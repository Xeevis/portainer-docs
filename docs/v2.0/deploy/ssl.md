# Secure Portainer using SSL

By default, Portainer’s web interface and API is exposed over HTTP. This is not secured, it’s recommended to enable SSL in a production environment.

To do so, you can use the following flags <code>--ssl</code>, <code>--sslcert</code> and <code>--sslkey</code>:

<pre><code>$ docker run -d -p 443:9000 -p 8000:8000 --name portainer --restart always -v /var/run/docker.sock:/var/run/docker.sock -v ~/local-certs:/certs -v portainer_data:/data portainer/portainer-ce --ssl --sslcert /certs/portainer.crt --sslkey /certs/portainer.key</code></pre>

Now, you can navigate to https://$ip-docker-host

## Notes

Do you think that is missing something here? Contribute with this admin guide forking the repo [Portainer-Docs](https://github.com/portainer/portainer-docs) and propose changes.