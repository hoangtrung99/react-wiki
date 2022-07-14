# React Environment

##### Install Node LTS Version via nvm

**Install [nvm](https://github.com/nvm-sh/nvm)**

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```

```bash
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```

**Install [node](https://nodejs.dev/)**

```bash
nvm install lts/*
``` 

##### Install tool for deployment
**[PM2 - Production process manager for Node.js](https://github.com/Unitech/pm2)**

```bash
npm install -g pm2
```

**[vercel/serve - Static file serving and directory listing](https://github.com/vercel/serve)**

```bash
npm install -g serve
```

**[nginx - Static file serving and directory listing](https://github.com/vercel/serve)**

```bash
sudo apt update
sudo apt install nginx
```
---

##### NextJs (coming soon...)

```bash
pm2 start yarn --name nextjs-project -- start [-p <port>]
```

```bash
pm2 start yarn --name next-export -- serve <export outDir> -l <port>
```
Not finished, I will write more...


##### ViteJs
```bash
pm2 start yarn --name vite-project -- preview --host [-p <port>]
```

```bash
pm2 start yarn --name vite-project -- serve -s <build outDir> -l <port>
```
Not finished, I will write more...

##### Config nginx
```nginx
```


##### More source
- [nginxconfig.io(NGINX config generator on steroids)](https://github.com/digitalocean/nginxconfig.io)
- [Deploy NextJS, CouldFront, AWS S3]()
- [NextJS, Nginx config](https://gist.github.com/ZaHuPro/2ecdb934a7362e979e3aa5a92b181153)