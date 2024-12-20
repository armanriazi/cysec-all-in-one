---

keywords: nmap,nslookup,dig,fierce,metagoofil,google,exiftool,shodanhq

---

# Using Backtrack tools and commands

Certainly! Below is a table summarizing the use cases of the specified tools:

| **Tool**       | **Use Case**                                                                                                       |
|----------------|---------------------------------------------------------------------------------------------------------------------|
| **Nmap**       | Network exploration and security auditing tool used to discover hosts and services on a network.                   |
| **nslookup**   | Command-line tool for querying DNS to obtain domain name or IP address mapping information.                        |
| **dig**        | DNS lookup tool used to query DNS servers for information about hostaddresses, mail exchanges, and more.           |
| **Fierce**     | Domain scanner designed to locate non-contiguous IP space and domain names, useful in reconnaissance.              |
| **Metagoofil** | Tool for extracting metadata from public documents (PDFs, DOCs, etc.) found on the web to gather information about a target. |
| **ExifTool**   | Perl library and command-line application for reading, writing, and manipulating metadata in various file formats.   |
| **shodanhq**   | Search engine that lets users find specific types of devices connected to the internet and their associated data.   |
| **imcarmen**   | Information gathering and reconnaissance in security assessments, gathering info about a target based on its IP address or domain name.It may also refer to a specific script or an app that isn't mainstream or widely adopted.   |


## Data

### Generate Data

```bash
nmap -vv -O -sS -A -p- P0 -oA nmapScan 127.0.0.1
```

## Detection

### Methods of detection

- DSINT هوش متن باز
- Footprint

### Types of detection systems

- IDS
- IPS

### Detection of DNS records

Like:

- CNAME
- A
- MX

### NsLookup

To change default name server to a new ip or name:

```bash
nslookup -type=ns example.com 156.154.70.22
```

Write a script:

nano AutoM8

```bash
for HOSTNAME in `cat DomainNames.txt`
do
echo "Getting name servers for [$HOSTNAME]" nslookup -type=ns $HOSTNAME 8.8.8.8
done 
```

```bash
sudo nano ./DomainNames.txt
#
{
example.com
example.net
example.org
}
```

```bash
chmod +x AutoM8
./AutoM8 >NameServerListing.txt
cat NameServerListing.txt
```

About transfer domain: `Zonetransfer.me`

### Dig is a replacement of nslookup

[T1]

Dig[T1] will use NSs that exists in the `/etc/resolve.conf`

```bash
dig +qr www.example.com any
```

Any means any records that contains keywords of any.

#### AXFR

axfr will provide all of the information about a ns.

```bash
dig @ns1.example.com example.com axfr
```

In the output we expect to see all sub domains.

#### Showing a benificial summery than prior cammands

```bash
dig +nocmd +noall +answer example.com
```

#### Reverse name by ip

```bash
dig +nocmd +noall +answer -x 192.168.0.1
```

#### Muiltiple query

```bash
dig +nocmd +noall +answer example.com example.net -X 192.168.1.10
```

#### Tracing

```bash
dig +trace example.com
```

#### Categorized

```bash
sudo ./nano diginIt.txt
#
+nocmd +noall +answer example.com
+nocmd +noall +answer example.net
+nocmd +noall +answer example.org ns
```

```bash
dig -f diginIt.txt
```

## Attacking to NSs

[S1]

### Fierce Tool

To find ip ranges that are not sequential.
Default used hostnames are saved in the hosts.txt of installed fierece folder.

```bash
cd /pentest/enumeration/dns/fierce
./fierce.pl -h
./fierce.pl -dns exapmle.com
```

#### Creating a private list

```bash
sudo nano ./myWordList.txt
```

{
irc
mail
mail1
testmachine1
testmachine
www
www1
ns
}

```bash
./fierce.pl -dns example.com -wordlist myWordList.txt
```

### verfying NSs

Websites:

- AFRINIC
- APNIC
- ARIN
- IANA
- ICANN
- LACINC
- NRO
- RIPE
- InterNic

## Gathering data

### Penetation to Google

#### Tools

- [ExploitDB with google dorks](../database/google.md)

### Metagoofil

[S1]

Sample:

```bash
metagoofil.py -d microsoft.com -t doc,pdf -l 200 -n 50 -o microsodtfiles -f results.html
```

Use-case:

```bash
phyton metagoofil.py -d example.com -t doc,pdf -l 200 -n 50 -o examplefiles -f results.html
```

Output a list of:

- users
- software
- paths & servers
- emails

<p align="center">
  <img src="..\assets\images\tools1.jpg" alt="Google Filters">
</p>

```bash
# Local dir analysis
metagoofil.py -h yes -o microsoftfiles -f results.html
```

### Tool to find MetaData

#### Hidden files

- Foca[T3] for windows

#### Images

```bash
./exiftool  t/images/FotoStation.jpg/ppt
```

### of an IP

```bash
whois example.com
```

Whois the name service of registerd a domain?

```bash
whois -h whois.apnic.net 192.0.43.10
```

```bash
whois -h whois.arin.net 192.0.43.10 | grep Country:
```

## Footprint Detection

### Search Engine

- [Showing IOT devices](../searchengine/shodanhq.md)

### Http

Showing for example X-Power-By: ASP.NET

```bash
nc example.com 80
```
