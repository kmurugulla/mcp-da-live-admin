# DA Admin MCP Server

Manage DA Live content via MCP - create block libraries, templates, placeholders from your code/pages.

## Quick Start

**1. Get your DA token:**
   - Login to [da.live](https://da.live) → [Use this bookmarklet](#da-token-bookmarklet) → Copy token

**2. Add to Cursor MCP settings:**
   ```json
   "da-live-admin": {
     "command": "npx",
     "args": ["https://github.com/kmurugulla/mcp-da-live-admin"],
     "env": {
       "DA_ADMIN_API_TOKEN": "your_token_here"
     }
   }
   ```

**3. Ask Cursor:**
   ```
   Set up block library in myorg/myrepo
   ```

---

## <span id="da-token-bookmarklet">DA Token Bookmarklet</span>

Login to [da.live](https://da.live), create a bookmark with this code, click it to copy your token:

```javascript
javascript:(function(){try{const keys=Object.keys(localStorage).filter(k=>k.startsWith('adobeid_ims_access_token'));if(!keys.length){alert('Token not found. Make sure you are on da.live');return;}let token,expire;for(const k of keys){const data=JSON.parse(localStorage.getItem(k));if(data.valid){token=data.tokenValue;expire=data.expire;break;}}if(!token){alert('No valid token found. Please login again.');return;}navigator.clipboard.writeText(token).then(()=>{const expireDate=expire?new Date(expire).toLocaleString():'Unknown';alert(`Token copied to clipboard!\n\nExpires: ${expireDate}`);}).catch(()=>{const t=document.createElement('textarea');t.value=token;document.body.appendChild(t);t.select();document.execCommand('copy');document.body.removeChild(t);alert('Token copied!');});}catch(e){alert('Error: '+e.message);}})();
```

*Note: Tokens expire after ~24 hours. For production use, apply to [Adobe Prerelease Program](https://www.adobeprerelease.com/beta/B3739D7D-1860-4197-9378-52EC0E75B1E5/apply).*

---

## Common Commands

**Block Library:**
```
Set up block library in org/repo with example content from homepage
Add Cards block to library in org/repo with examples from /demo
```

**Templates:**
```
Create template "Blog" from /blogs/article in org/repo
Update template "Blog" from /blogs/new-article in org/repo
```

**Placeholders:**
```
Add placeholder "Phone" = "1-800-123-4567" in org/repo
Update placeholder "Phone" to "1-800-999-8888" in org/repo
```

**Media:**
```
Show unused media in org/repo
Find images missing alt text in org/repo
```

---

## Features

- **Block Library Setup** - Auto-generate block docs from local/GitHub code with real content examples
- **Template Management** - Create/update templates from existing pages
- **Placeholder Management** - Manage site-wide placeholders
- **Icon Management** - Register and organize icons
- **Media Audit** - Find unused media, missing alt text, check accessibility
- **Content Operations** - List, get, create, delete source content

---

<details>
<summary><h2>📚 All Commands Reference</h2></summary>

### Block Library Commands

**Setup complete library:**
```
Set up block library in org/repo with example content from homepage and /demo pages
```

**Add single block:**
```
Add Cards block to library in org/repo with example from /drafts/card-demo
Update Cards block documentation with example from /drafts/new-demo in org/repo
```

**Remove block:**
```
Delete Cards block from library in org/repo
```

### Template Commands

**Create:**
```
Create template "Blog" from /blogs/article in org/repo
```

**Update:**
```
Update template "Blog" from /blogs/new-article in org/repo
```

**Delete:**
```
Delete template "Blog" from library in org/repo
```

### Placeholder Commands

**Add:**
```
Add placeholder "Telephone" = "1-800-123-4567" in org/repo
```

**Update:**
```
Update placeholder "Telephone" to "1-800-999-8888" in org/repo
```

**Delete:**
```
Delete placeholder "Telephone" in org/repo
```

### Media Commands

**Audit:**
```
Show unused media in org/repo
Find images missing alt text in org/repo
Get media statistics for org/repo
```

**Search:**
```
Find all PNGs in org/repo
Show images used in /blogs/article in org/repo
```

### Content Commands

**List:**
```
List sources in /path in org/repo
```

**Get:**
```
Get source content at /path in org/repo
```

**Create/Delete:**
```
Create source content at /path in org/repo
Delete source content at /path in org/repo
```

</details>

---

## Contributing

1. Fork the repository
2. Create feature branch
3. Commit changes
4. Push and create Pull Request

## License

MIT
