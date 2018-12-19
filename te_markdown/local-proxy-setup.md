---
layout: page
title: Local Proxy Setup
permalink: /te_markdown/local-proxy-setup/
---

Estimated reading time: 3 minutes


## Setup environment variable
**Test-Editor-Web** can be used behind a proxy server. You'll need an environment variable named `http_proxy` which look like this:

```
http_proxy=http://myUsername:myPassword@proxy.server.address:80
```

Out of this environment variable the tutorial scripts extract
1. proxy user name
2. proxy user password
3. proxy server url
4. proxy server port

In our above example this would be :
1. myUsername
2. myPassword
3. proxy.server.address
4. 80

:warning: Keep in mind, that your username, password and proxy server url should not contain following characters
`:` or  `@` or `"` or `'` or `//` :warning:


### Setup under Linux
Just export the enviromment variable with the linux command on a terminal.
Open a shell in the respective folder and use the following commands:

```
cd heroes                          # switch to the heroes tutorial
bash export http_proxy=http://myUsername:myPassword@proxy.server.address:80 
```

### That's it 
If you succesfully set up the environment variable, nothing else has to be done.   
After this step you can start a fresh, clean version of the first tutorial (e.g. creating a test specification).

You want to know more about how to install the Test-Editor-Web, getting started to write specifications? [read more](/te_markdown/local-setup){:class="web-button-grey reduced-padding"}

If you want to know more about how specifications can and should be written [read more](/te_markdown/test-specifications){:class="web-button-grey reduced-padding"}

You can find all tutorials and a brief desription [here](https://github.com/test-editor/tutorials )
