# WAPT-XSS-Cross-Site-Scripting-with-XSSer
Perform XSS attack with XSSer. I show only the important steps required to perform the attack, so, I didn’t explain everything.
# Introduction of the tool
XSSer is a tool that can help you to perform cross site scripting attacks on web-based applications. Cross site scripting (XSS) is a type of attack that allows an attacker to inject malicious code into a web page that is viewed by other users, which can result in stealing cookies, session hijacking, phishing, or defacing websites. XSSer can do various tasks, such as:<br>
- Detecting XSS vulnerabilities in web applications using different techniques and vectors.<br>
- Exploiting XSS vulnerabilities by injecting code that can bypass filters, execute commands, or establish reverse connections.<br>
- Reporting XSS vulnerabilities by generating reports in different formats, such as HTML, XML, JSON, or CSV.<br>
XSSer is a command-line tool that can be used on any platform that supports Python. It has a powerful detection engine and a wide range of options and features that make it a versatile and effective tool for penetration testing and vulnerability assessment.<br>

**Cross Site Scripter is an automatic -framework- to detect, exploit and report XSS vulnerabilities in web-based applications.** <br>

### Usage:
xsser [OPTIONS] [--all <url> |-u <url> |-i <file> |-d <dork> (options)|-l ] [-g <get> |-p <post> |-c <crawl> (options)] [Request(s)] [Checker(s)] [Vector(s)] [Anti-antiXSS/IDS] [Bypasser(s)] [Technique(s)] [Final Injection(s)] [Reporting] {Miscellaneous} <br>

## *Options*:
   - --version             show program's version number and exit<br>
   - -h, --help            show this help message and exit<br>
   - -s, --statistics      show advanced statistics output results<br>
   - -v, --verbose         active verbose mode output results<br>
   - --gtk                 launch XSSer GTK Interface<br>
   - --wizard              start Wizard Helper!

  ## *Special Features*:
    You can set Vector(s) and Bypasser(s) to build complex scripts for XSS
    code embedded. XST allows you to discover if target is vulnerable to
    'Cross Site Tracing' [CAPEC-107]:

    --imx=IMX           IMX - Create an image with XSS (--imx image.png)
    --fla=FLASH         FLA - Create a flash movie with XSS (--fla movie.swf)
    --xst=XST           XST - Cross Site Tracing (--xst http(s)://host.com)

  ## *Select Target(s)*:
    At least one of these options must to be specified to set the source
    to get target(s) urls from:

    --all=TARGET        Automatically audit an entire target
    -u URL, --url=URL   Enter target to audit
    -i READFILE         Read target(s) urls from file
    -d DORK             Search target(s) using a query (ex: 'news.php?id=')
    -l                  Search from a list of 'dorks'
    --De=DORK_ENGINE    Use this search engine (default: DuckDuckGo)
    --Da                Search massively using all search engines

  ## *Select type of HTTP/HTTPS Connection(s)*:
    These options can be used to specify which parameter(s) we want to use
    as payload(s). Set 'XSS' as keyword on the place(s) that you want to
    inject:

    -g GETDATA          Send payload using GET (ex: '/menu.php?id=XSS')
    -p POSTDATA         Send payload using POST (ex: 'foo=1&bar=XSS')
    -c CRAWLING         Number of urls to crawl on target(s): 1-99999
    --Cw=CRAWLER_WIDTH  Deeping level of crawler: 1-5 (default: 2)
    --Cl                Crawl only local target(s) urls (default: FALSE)

  ## *Configure Request(s)*:
    These options can be used to specify how to connect to the target(s)
    payload(s). You can choose multiple:

    --head              Send a HEAD request before start a test
    --cookie=COOKIE     Change your HTTP Cookie header
    --drop-cookie       Ignore Set-Cookie header from response
    --user-agent=AGENT  Change your HTTP User-Agent header (default: SPOOFED)
    --referer=REFERER   Use another HTTP Referer header (default: NONE)
    --xforw             Set your HTTP X-Forwarded-For with random IP values
    --xclient           Set your HTTP X-Client-IP with random IP values
    --headers=HEADERS   Extra HTTP headers newline separated
    --auth-type=ATYPE   HTTP Authentication type (Basic, Digest, GSS or NTLM)
    --auth-cred=ACRED   HTTP Authentication credentials (name:password)
    --check-tor         Check to see if Tor is used properly
    --proxy=PROXY       Use proxy server (tor: http://localhost:8118)
    --ignore-proxy      Ignore system default HTTP proxy
    --timeout=TIMEOUT   Select your timeout (default: 30)
    --retries=RETRIES   Retries when connection timeout (default: 1)
    --threads=THREADS   Maximum number of concurrent requests (default: 5)
    --delay=DELAY       Delay in seconds between each request (default: 0)
    --tcp-nodelay       Use the TCP_NODELAY option
    --follow-redirects  Follow server redirections (default: FALSE)
    --follow-limit=FLI  Set limit for redirection requests (default: 50)

  ## *Checker Systems*:
    These options are useful to know if your target is using filters
    against XSS attacks:

    --hash              Send a hash to check if target is repeating content
    --heuristic         Discover parameters filtered by using heuristics
    --discode=DISCODE   Set code on reply to discard an injection
    --checkaturl=ALT    Check reply using: <alternative url> [aka BLIND-XSS]
    --checkmethod=ALTM  Check reply using: GET or POST (default: GET)
    --checkatdata=ALD   Check reply using: <alternative payload>
    --reverse-check     Establish a reverse connection from target to XSSer

  ## *Select Vector(s)*:
    These options can be used to specify injection(s) code. Important if
    you don't want to inject a common XSS vector used by default. Choose
    only one option:

    --payload=SCRIPT    OWN   - Inject your own code
    --auto              AUTO  - Inject a list of vectors provided by XSSer

  ## *Select Payload(s)*:
    These options can be used to set the list of vectors provided by
    XSSer. Choose only if required:

    --auto-set=FZZ_NUM  ASET  - Limit of vectors to inject (default: 1293)
    --auto-info         AINFO - Select ONLY vectors with INFO (default: FALSE)
    --auto-random       ARAND - Set random to order (default: FALSE)

  ## *Anti-antiXSS Firewall rules*:
    These options can be used to try to bypass specific WAF/IDS products
    and some anti-XSS browser filters. Choose only if required:

    --Phpids0.6.5       PHPIDS (0.6.5) [ALL]
    --Phpids0.7         PHPIDS (0.7) [ALL]
    --Imperva           Imperva Incapsula [ALL]
    --Webknight         WebKnight (4.1) [Chrome]
    --F5bigip           F5 Big IP [Chrome + FF + Opera]
    --Barracuda         Barracuda WAF [ALL]
    --Modsec            Mod-Security [ALL]
    --Quickdefense      QuickDefense [Chrome]
    --Sucuri            SucuriWAF [ALL]
    --Firefox           Firefox 12 [& below]
    --Chrome            Chrome 19 & Firefox 12 [& below]
    --Opera             Opera 10.5 [& below]
    --Iexplorer         IExplorer 9 & Firefox 12 [& below]

  ## *Select Bypasser(s)*:
    These options can be used to encode vector(s) and try to bypass
    possible anti-XSS filters. They can be combined with other techniques:

    --Str               Use method String.FromCharCode()
    --Une               Use Unescape() function
    --Mix               Mix String.FromCharCode() and Unescape()
    --Dec               Use Decimal encoding
    --Hex               Use Hexadecimal encoding
    --Hes               Use Hexadecimal encoding with semicolons
    --Dwo               Encode IP addresses with DWORD
    --Doo               Encode IP addresses with Octal
    --Cem=CEM           Set different 'Character Encoding Mutations'
                        (reversing obfuscators) (ex: 'Mix,Une,Str,Hex')

  ## *Special Technique(s)*:
    These options can be used to inject code using different XSS
    techniques and fuzzing vectors. You can choose multiple:

    --Coo               COO - Cross Site Scripting Cookie injection
    --Xsa               XSA - Cross Site Agent Scripting
    --Xsr               XSR - Cross Site Referer Scripting
    --Dcp               DCP - Data Control Protocol injections
    --Dom               DOM - Document Object Model injections
    --Ind               IND - HTTP Response Splitting Induced code

  ## *Select Final injection(s)*:
    These options can be used to specify the final code to inject on
    vulnerable target(s). Important if you want to exploit 'on-the-wild'
    the vulnerabilities found. Choose only one option:

    --Fp=FINALPAYLOAD   OWN    - Exploit your own code
    --Fr=FINALREMOTE    REMOTE - Exploit a script -remotely-

  ## *Special Final injection(s)*:
    These options can be used to execute some 'special' injection(s) on
    vulnerable target(s). You can select multiple and combine them with
    your final code (except with DCP exploits):

    --Anchor            ANC  - Use 'Anchor Stealth' payloader (DOM shadows!)
    --B64               B64  - Base64 code encoding in META tag (rfc2397)
    --Onm               ONM  - Use onMouseMove() event
    --Ifr               IFR  - Use <iframe> source tag
    --Dos               DOS  - XSS (client) Denial of Service
    --Doss              DOSs - XSS (server) Denial of Service

  ## *Reporting*:
    --save              Export to file (XSSreport.raw)
    --xml=FILEXML       Export to XML (--xml file.xml)

  ## *Miscellaneous*:
    --silent            Inhibit console output results
    --alive=ISALIVE     Set limit of errors before check if target is alive
    --update            Check for latest stable version





## XSS with XSSer
We perform the attack on OWASP Mutillidae II. <br>
### Goal: Get some payloads to perform XSS (POST). <br>
Use nmap to scan the network and identify the ports that are running the http and mysql services. The ports must be OPEN.<br>
1. Start Burp Proxy in interception mode and active FoxyProxy from browser to capture the http request.<br>
2. In the page vulnerable to XSS write something in the form and click search to intercept the request POST.
3. Replace the value of the parameter that reflects the value entered on the web page with XSS
4. Run the command:<b> xsser --url 'referer of the request' -p 'payload of the POST request with XSS value'</b>. 
<br> <img src="result_xss2.png" width=100% height="auto"><br>

You can also try use various XSS payloads in auto mode:<b> xsser --url 'referer of the request' -p 'payload of the POST request with XSS value' --auto</b> or use custom payload<b> xsser --url 'referer of the request' -p 'payload of the POST request with XSS value' --Fp "<script>alert(1)</script>"</b> and open the final attack link to trigger the XSS vulnerability in the browser

### Goal: Get some payloads to perform XSS (GET). <br>
Use nmap to scan the network and identify the ports that are running the http and mysql services. The ports must be OPEN.<br>
1. In the page vulnerable to XSS select one option in the list and click submit vote to check the url.
2. Perform the scanning of payloads:<b> xsser --url “url with variable=XSS”</b>
<br> <img src="result_xss.png" width=100% height="auto"><br>

You can use your custom script:<b> xsser --url “url with variable=XSS” --Fp "<script>alert(1)</script>"</b> and open the final attack link to trigger the XSS vulnerability in the browser<br><br>
**XSS with auth**<br>
 - xsser --url “url with variable=XSS” --cookie=”cookie”  <br>

#Author
<b>Xiao Li Savio Feng</b>
