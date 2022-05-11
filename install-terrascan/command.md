

- The following is a description of all the commands available. Terrascan’s interface is divided into subcommands as follows: <br>

init = Initializes Terrascan by downloading the latest Rego policies into ~/.terrascan. The scan command will implicitly run this before a scan if it detects that there are no policies found. <br>
scan = scans Infrastructure as code files based on the policies contained within the “.terrascan” directory <br>
server = Starts the Terrascan’s API server <br>
help = You can view the usage menu by typing help or using the -h flag on any subcommand (e.g. terrascan init -h). You can also view this by typing terrascan without flags or other arguments. <br>

 ## Terrascan Commands 
```
$ Terrascan

Detect compliance and security violations across Infrastructure as Code to mitigate risk before provisioning cloud native infrastructure.
For more information, please visit https://docs.accurics.com

Usage:
  terrascan [command]

Available Commands:
  help        Help about any command
  init        Initializes Terrascan and clones policies from the Terrascan GitHub repository.
  scan        Detect compliance and security violations across Infrastructure as Code.
  server      Run Terrascan as an API server
  version     Terrascan version

Flags:
  -c, --config-path string   config file path
  -h, --help                 help for terrascan
  -l, --log-level string     log level (debug, info, warn, error, panic, fatal) (default "info")
  -x, --log-type string      log output type (console, json) (default "console")
  -o, --output string        output type (human, json, yaml, xml, junit-xml, sarif, github-sarif) (default "human")

Use "terrascan [command] --help" for more information about a command.

```

Initializes Terrascan and clones policies from the Terrascan GitHub repository.
```
terrascan init
```{{exec}}
the initalization process download the latest Rego policies [repository ](https://github.com/accurics/terrascan) into ~/.terrascan. The scan command will implicitly run this before a scan if it detects that there are no policies found.

