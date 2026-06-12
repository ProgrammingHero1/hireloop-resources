## Server Deployment steps

1. comment await commands outside api methods for solving gateway timeout error

```js
//comment following commands

await client.db("admin").command({ ping: 1 });
```

2. Mongodb whitelist

MongoDB Atlas IP Whitelist: Atlas → Network Access → Add IP Address → 0.0.0.0/0 (allow all) 


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

5. vercel login
```
vercel login
```

6. Deploy to Vercel

```bash

vercel
vercel --prod
- After completed the deployment . click on inspect link and copy the production domain
```

7. Terminal Questions
? Set up and deploy? → Yes
? Which scope? → Select Your account 
? Link to existing project? → No
? What's your project's name? → my-app-backend
? In which directory is your code located? → ./
? Want to override the settings? → No



8. Setup your environment variables in vercel


9. API for data 

<img src="https://i.ibb.co.com/dgH40d3/Screenshot-3.jpg"/>


10. Test the API (public/open api)
# Server Deployment on Vercel  Done
