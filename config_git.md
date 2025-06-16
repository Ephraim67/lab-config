###  What You’ll Achieve

A URL like:

```
https://yourusername.github.io/lab-config/config.json
```

That your Python client can fetch even if your main server is down.

---

##  Step-by-Step Guide: Hosting on GitHub Pages



###  Step 1: Create a GitHub Repository

1. Go to [https://github.com](https://github.com) and sign in.
2. Click **New Repository**.
3. Fill in:

   * **Repository name**: `lab-config` (or anything you like)
   * **Public** (important for GitHub Pages to work)
   * ✅ Check **“Add a README file”**
4. Click **Create repository**



###  Step 2: Add `config.json`

1. On your repo page, click **Add file → Create new file**
2. Name it exactly: `config.json`
3. Paste the contents like this:

```json
{
  "server_ip": "your-server-ip-or-domain",
  "server_port": 9999
}
```

4. Scroll down and click **Commit new file**



### Step 3: Enable GitHub Pages

1. Go to the **Settings** tab of your repo
2. Scroll down to **Pages** on the sidebar (or go to `https://github.com/YOUR_USERNAME/lab-config/settings/pages`)
3. Under **"Source"**, select:

   * Branch: `main`
   * Folder: `/ (root)`
4. Click **Save**

 GitHub will display a URL like:

```
https://yourusername.github.io/lab-config/
```

Your file will now be live at:

```
https://yourusername.github.io/lab-config/config.json
```



### Step 4: Test the URL

In your browser or terminal:

```bash
curl https://yourusername.github.io/lab-config/config.json
```

You should see:

```json
{
  "server_ip": "your-server-ip-or-domain",
  "server_port": 9999
}
```



### Step 5: Update Your Python Client

Edit the Python client to use the new URL:

```python
CONFIG_URLS = [
    "https://yourusername.github.io/lab-config/config.json",
    # Add backups here if needed
]
```



###  (Optional) Troubleshooting

* If the link gives a 404, wait 1–2 minutes — GitHub Pages sometimes takes a short time to publish.
* Make sure your repo is **public**.
* Ensure the file is named `config.json`, not `config.json.txt`.


