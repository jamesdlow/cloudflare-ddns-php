# cloudflare-ddns
A simple PHP script that takes standard Dyanmic DNS params and then updates the Cloudfare API

# Instructions
1. Upload index.php to where you want to run the script.

2. Create a Cloudflare API token by following the URL below. You should be able to restrict to  just the DNS zone you want to update.
https://developers.cloudflare.com/fundamentals/api/get-started/create-token/

3. Create a A record for your desired subdomain with a TTL set to the frequency of update by your DDNS clients.

4. Setup your DDNS client/router as per:
- Username: {BLANK/ANYTHING}
- Password: {CLOUDFLARE_TOKEN}
- Hostname: {HOSTNAME}

5. It can also be called directly:
curl -u ":{CLOUDFLARE_TOKEN}" "https://{PATH_TO_SCRIPT}?hostname={HOSTNAME}"

# Notes
Cloudflare have some information about other ways to do this here:
https://developers.cloudflare.com/dns/manage-dns-records/how-to/managing-dynamic-ip-addresses/

DynDNS URL is as follows:
https://members.dyndns.org/nic/update?hostname={hostname}&myip={new_ip}

HTTP Basic Auth:
Authorization: Basic Base64({username}:{password})

No-IP uses the same structure:
https://dynupdate.no-ip.com/nic/update?hostname={hostname}&myip={new_ip}