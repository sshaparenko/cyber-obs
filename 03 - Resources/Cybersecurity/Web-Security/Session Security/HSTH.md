**HTTP Strict Transport Security** is a simple and widely supported standard to protect visitors by ensuring that their browsers always connect to a website over HTTPS

Header called `Strict-Transport-Security` used for this and can have the next parameters:

| Parameter           | Meaning                                                                             |
| ------------------- | ----------------------------------------------------------------------------------- |
| `max-age`           | Duration (in seconds) to tell a browser that requests are available only over HTTPS |
| `includeSubDomains` | The configuration is valid for the subdomain as well                                |
| `preload`           | User if you would like your domain to be included in the HSTS preload list          |
