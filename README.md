# njs
Base repo template for njs development

*Using with Docker CLI*
---

After customizing nginx.conf and your njs source files, use this to start up an nginx container:

docker run --rm -v $(pwd)/nginx.conf:/etc/nginx/nginx.conf:ro  -v $(pwd)/njs/:/etc/nginx/njs/:ro -p 80:80 -d nginx

*Using with Visual Studio Code*
---

The official nginx OSS Docker image is used.

After creating a new repo from this template in VS Code, you will be asked to open a devContainer.  Typescript declaration files for njs are installed to enable Intellisense and autocompletions.  See `hello.js` for an example of using the @param tag to inform VS Code about the `request` object in njs.

Devcontainer will bind mount nginx.conf and the njs directory from the workspace into /etc/nginx

Files in the workspace can be edited locally or in the container.  Just run `nginx -s reload` in a container terminal after saving a change.  In Visual Studio Code, you can trigger a reload in the devContainer by selecting **Run Build Task** (⇧⌘B)
