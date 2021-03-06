Python script to update DNS A record of your domain dynamically using gandi.net LiveDNS API:

http://doc.livedns.gandi.net/

The script was developed for those behind a dynamic IP interface (e.g. home server/pi/nas).

The config-template.txt file should be renamed to config.txt, and modified with your gandi.net API key, domain name, and A-record (@, dev, home, pi, etc).

Every time the script runs, it will query an external service to retrieve the external IP of the machine, compare it to the current A record in the zone at gandi.net, and then update the record if the IP has changed.

Requirements:
  - Python 2.7
  - ipaddress module (pip install ipaddress)
  - requests module (pip install requests)
  - json module (pip install json)

You can then run the script as a cron job :

```
*/15 * * * * python /home/user/gandi-ddns.py
```
