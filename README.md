# Visual Studio Code - Fauxpilot Client - 0xhaggis multiline fork

### Bleeding edge software. Caveat emptor!
Good luck, brave soul.

### Get up and running
Follow the instructions on the [original vscode-fauxpilot page](https://github.com/Venthe/vscode-fauxpilot). 

To build the extension and debug it you may need:

```
npm i --save-dev webpack webpack-cli ts-loader  # really needed?
npm run package
# now hit F5
```

### Multi-line completion for Python
It works ok for Python, especially if you ask it for things in comments. For example:

```python
import sys

# function to connect to host 'hostname' on port 'port' and return a socket. Handle all errors gracefully.
```

Fauxpilot will return something like this for a completion:

```python
def connect(host, port):
    try:
        s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        s.connect((host, port))
        return s
    except socket.error as e:
        print("Error connecting to %s:%s" % (host, port))
        print(e)
        sys.exit(1)
```

Just hit `tab` and voila, fully-written function.

### Other languages
It sucked for C in a quick test, but other LLMs might work better than the [default fauxpilot server LLM](https://github.com/fauxpilot/fauxpilot). More testing soon. 
