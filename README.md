# Hosting-panel :- **CHUNK DASH**

**How to Install**

# Repo Clone & Cd in Dash
```
git clone https://github.com/deadlauncherg/Hosting-panel.git
cd Hosting-panel || exit
```
# Install nvm
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```
# nvm Exporter
```
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
```
# Reload nvm source
```
source ~/.bashrc
```
# Install nvm Latest & Verify version
```
nvm install 18
nvm use 18
nvm alias default 18
node -v
npm -v    
```
# Install sudo,do update & install npm
```
apt install sudo
sudo apt update
npm install
```
# If Using ipv4 Vps

# Install Nginx & Certbot
```
apt install nginx && apt install certbot
```
# Allow Ports
```
ufw allow 80 && ufw allow 443
```
# Add  Domain
```
certbot certonly -d <Your Domain>
```
# nano configure for proxy
```
nano /etc/nginx/sites-enabled/heliactyl.conf
```
# Proxy configure
```
server {
    listen 80;
    server_name <domain>;
    return 301 https://$server_name$request_uri;
}

server {
    listen 443 ssl http2;

    location /ws {
      proxy_http_version 1.1;
      proxy_set_header Upgrade $http_upgrade;
      proxy_set_header Connection "upgrade";
      proxy_pass "http://localhost:<port>/ws";
    }

    server_name <domain>;

    ssl_certificate /etc/letsencrypt/live/<domain>/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/<domain>/privkey.pem;
    ssl_session_cache shared:SSL:10m;
    ssl_protocols SSLv3 TLSv1 TLSv1.1 TLSv1.2;
    ssl_ciphers  HIGH:!aNULL:!MD5;
    ssl_prefer_server_ciphers on;

    location / {
      proxy_pass http://localhost:<port>/;
      proxy_buffering off;
      proxy_set_header X-Real-IP $remote_addr;
    }
}
```
# Nginx restart
```
systemctl restart nginx
```
# How to start 
- Run `node .` on the vps to start Dashboard
- Make Sure Configure you settings.json according to Your wish

# If Using Non ipv4 Vps

# Easy and One Line cmd
```
bash <(curl -fsSL https://raw.githubusercontent.com/deadlauncherg/debian-vm/main/install.sh)
```
# How to start 
- Run `node .` on the vps to start Dashboard
- Before This Configure Your Cloudflare Tunnel By This video **[Video]([https://www.youtube.com/watch?v=W3OmNBE4k5w)**.
- After This Setup settings.json
- After this all process Do Only `Node .` to start your Dashboard
- Now Your Dashboard is accessable with your Forwaded Cloudflare Domain
- 
## 🙌 Credits

This project is proudly developed and maintained by **[LapioGaming](https://www.youtube.com/@LapioGaming)**.  

⚠️ **Note:** If you make any modifications, forks, or redistributions of this repository, please provide proper credit to **LapioGaming** by including the link above in your project. Respecting credits helps keep the community fair and supports further development.  

# Login Page
![imgonline-com-ua-convert82YF3sx3K3EA](https://github.com/user-attachments/assets/62b694ac-2aeb-4e0c-ba17-254e618ca971)

