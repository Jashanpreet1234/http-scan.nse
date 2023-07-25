**# http-scan.nse**
http-scan.nse is a script that is included in the Nmap Scripting Engine (NSE) library. It is designed to perform basic scanning and information gathering on HTTP services.

HTTP scan refers to the process of scanning web servers and applications for vulnerabilities and weaknesses. It involves sending various HTTP requests to a target server and analyzing the responses to identify potential security issues. HTTP scanning can be used by security professionals, ethical hackers, or malicious attackers to assess the security posture of a web server or application. The scan may look for common vulnerabilities such as outdated software versions, misconfigurations, weak authentication mechanisms, or known exploits.

**The startup script**

bash script.sh &


-- HEAD
local stdnse = require "stdnse"
local shortport = require "shortport"

description = [[
  A script to see if http-alt is open and print information about it.
]]

author = "Your Name"

license = "Same as Nmap--See https://nmap.org/book/man-legal.html"

categories = {"safe"}

#The port rule is scanning for http-alt on port 8000. This is to check if the port is open 

-- RULES
portrule = shortport.port_or_service(8000, "http-alt")

# this functions takes in two argument: one host and port and port is the one by which the msg will be returned

-- ACTION
action = function(host, port)
return port.version.name .. " is " .. port.state .. " and running on port number " .. port.number .. "."

 end
