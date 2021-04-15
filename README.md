# URL SHORTENER

**FROM:**  
[netlify-shortener](https://github.com/kentcdodds/netlify-shortener)
---
### STEPS TO REPLICATE
1. Create a new github repository
2. Create a new file named `_redirects` in that repository
3. Copy and paste this into your new `_redirects` file (making modifications as you see fit):
```bash
# this is an example '_redirect' file
# examples below if your domain is 'chz.com'

# chz.com/foo will redirect to https://exmaple.com/foo
/foo       https://example.com/foo

# chz.com/example will redirect to https://example.com
/example   https://example.com

# chz.com/github will redirect to https://github.com/chz
/github    https://github.com/chz

# chz.com will redirect to google.com
/*         https://google.com
```
4. Commit new file
5. Create a new netlify account (if needed)
6. Add a new site from github in Netlify 
7. Select the repo created in step 1 and accept all the defaults (deploy the main branch with no build settings)
8. Click deploy site
9. Clone the repo to your local workstation (npm required)
10. create package.json (`npm init -y`)
11. install modules (`npm install --save-dev netlify-shortener`)
12. in `package.json`, add a script for `npm shorten`, like the following:
```json
"scripts": {
  "shorten": "netlify-shortener"
  },
```
13. add `npm_modules` to your git ignore (`echo "npm_modules" > .gitignore`)
14. add, commit and push changes to your github repo
15. run `npm run shorten` 
16. go to `chz.com/foo` to test (from example above)
17. to add redirects, run `npm run shorten https://youtube.com youtube` which will redirect `chz.com/youtube` to `https://youtube.com` (example)

**NOTE:** This will automatically deploy your site in netlify by committing and pushing to github, so there's no manual intervention. It will also copy the link to your clipboard, so you can enter into your browser

---
### VIDEO WALKTHROUGH:
[https://youtu.be/HL6paXyx6hM](https://youtu.be/HL6paXyx6hM)
