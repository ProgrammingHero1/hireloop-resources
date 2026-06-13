## Server Deployment steps

1. comment await commands outside api methods for solving gateway timeout error

```js
//comment following commands

await client.db("admin").command({ ping: 1 });
```

at the top level can cause Vercel serverless cold-start delays because it runs during module initialization.

2. Mongodb whitelist
```
 Atlas → Network Access → Add IP Address → 0.0.0.0/0 (allow all) 

For development only:
0.0.0.0/0

For production:
Allow only your deployment provider IPs if possible.
```
3. create vercel.json file for configuring server

```json
{
  "version": 2,
  "builds": [
    {
      "src": "index.js",
      "use": "@vercel/node"
    }
  ],
  "routes": [
    {
      "src": "/(.*)",
      "dest": "index.js",
      "methods": ["GET", "POST", "PUT", "PATCH", "DELETE", "OPTIONS"]
    }
  ]
}
```

4. install vercel 
```
npm install -g vercel
```


5. Add start script check

Before deployment: `package.json`

```
"scripts": {
  "start": "node index.js"
}
```
Vercel needs the entry point.

6.Create an account using email/ github in [vercel ](https://vercel.com/)
  
and then in the command line of your computer now: vercel login
```
vercel login
```

7. Deploy to Vercel

```bash

vercel
vercel --prod
- After completed the deployment . click on inspect link and copy the production domain
```

8. Terminal Questions
? Set up and deploy? → Yes
? Which scope? → Select Your account 
? Link to existing project? → No
? What's your project's name? → my-app-backend
? In which directory is your code located? → ./
? Want to override the settings? → No



9. Setup your environment variables in vercel
```
Vercel Dashboard
→ Project
→ Settings
→ Environment Variables
→ Add

Example:

MONGODB_URI=mongodb+srv://...
JWT_SECRET=...
NODE_ENV=production
```

10. API for data 

<img src="https://i.ibb.co.com/dgH40d3/Screenshot-3.jpg"/>


11. Test the API (public/open api)
  Vercel serverless functions may have a cold start.
The first request can take a few seconds longer.
### Server Deployment on Vercel  Done
