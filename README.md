---
title: 'Academic: the website builder for Hugo'
subtitle: 'Create a beautifully simple website in under 10 minutes :rocket:'
summary: Create a beautifully simple website in under 10 minutes.
authors:
- campos
tags:
- Academic
categories:
- Demo
date: "2016-04-20T00:00:00Z"
lastmod: "2019-04-17T00:00:00Z"
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Placement options: 1 = Full column width, 2 = Out-set, 3 = Screen-width
# Focal point options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
image:
  placement: 2
  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/CpkOjOcXdUY)'
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

todo
tipos de deploy, canary, blue-green

# DevOps

![devops](https://img.shields.io/badge/Dev-Ops-blue.svg)
![License](https://img.shields.io/badge/Code%20License-MIT-blue.svg)
![github](https://img.shields.io/badge/Control%20Version-GitHub-brightgreen.svg)
![visitors](https://visitor-badge.laobi.icu/badge?page_id=brunocampos01/desenvolvimento-de-sistemas.visitor-badge)

<img src='images/devops.png' align="right" height=auto width=50%>

# Summary

- :penguin:**Linux**:penguin:
  - [Home Sweet home](https://github.com/brunocampos01/home-sweet-home)
  - [Shell Script]() # learning
  - [Network](#network)
  - [My Problems]() # create repository LINUX
    - [Agent Refused Operation](#agent-refused-operation)

- **Infrastructure As Code and Configuration Management** :computer: :computer: :computer:
  - [Scripts]() # learning
      - [Bash](infra-as-code/bash)
      - [PowerShell](infra-as-code/powershell)
  - [Chef](infra-as-code/chef/)
  - [Ansible](infra-as-code/ansible) # learning
  - [Terraform](infra-as-code/terraform)


- **Control Version** :black_circle::heavy_minus_sign::black_circle::heavy_minus_sign::red_circle:
  - Files Git
    - [Local Directory: .git]()
    - [.gitconfig](git/.gitconfig)
    - [.gitignore](git/gitignore-models)
    - [.gitattributes](git/) # in production https://github.com/github/linguist#overrides
    - [.gitkeep](git/)
  
  - Good Pratices :bookmark_tabs:
    - [Writing Commits](git/) 
    - [Writing Branches](git/) # in production
    - [Writing Readme](https://github.com/brunocampos01/DevOps/blob/master/github/como-escrever-README.md)
    - [Coding Styles: .editorconfig](git/.editorconfig)
    - [Types of LICENSE](https://choosealicense.com/)

  - Documentation (markdown) :page_with_curl:
    - [Basic writing](https://help.github.com/en/articles/basic-writing-and-formatting-syntax)
    - [Style guide](https://github.com/DavidAnson/markdownlint/blob/v0.13.0/doc/Rules.md#md025)
    - [Emojis](https://gist.github.com/rxaviers/7360908)
    - [Images](#images)
    - [Shields](https://shields.io/category/build)

- **Virtualization** :shell:
  - [Fundamentals]()
  - [Virtual Environment Python](https://github.com/brunocampos01/becoming-a-expert-python#virtual-environment) :snake:
  - [Containers](#containers)
    - [Fundamentals]()
      - Files Docker
        - [dockfile]()
        - [dockerignore]()
    - [Docker Comands](#docker-commands)
    - [Orchestrators](#orchestrators)
      - [Mesos](#Mesos)
      - [Marathon](#managemant-libraries)

  - [Cloud](#cloud)
    - [Azure](#azure)
    - [AWS CLI](#awscli)
    - [S3](#s3)
    - [EC2](#ec2)
      - [Secutiry](#s3)
      - [VPC](#VPC)
      - [Security Group](#security-group)

- **Continuos Integration and Continuous Delivery**
    - [Crontab](#crontab)
    - [Jenkins](#jenkins)
    - [Rundeck](#rundeck)
    - [Runbooks](#runbooks)


- **Monitoring** :hourglass_flowing_sand: :chart_with_upwards_trend:
    - In production ...

- **Logs** :page_facing_up:
    - In production ...

---


# Linux
# Packge Manager
```
```

### Structure Directory
...


## Wiping the entire disk
```
dd if=/dev/zero of=/dev/sdX bs=1M #replace X with the target drive letter.
```

Wiping the Master boot record (MBR)Edit
```
dd if=/dev/zero of=/dev/hdX bs=446 count=1 #replace X with the target drive letter.
```


## Processing Files and Data

- For JSON, use [`jq`](http://stedolan.github.io/jq/). For interactive use, also see [`jid`](https://github.com/simeji/jid) and [`jiq`](https://github.com/fiatjaf/jiq).

- For YAML, use [`shyaml`](https://github.com/0k/shyaml).

- For Excel or CSV files, [csvkit](https://github.com/onyxfish/csvkit) provides `in2csv`, `csvcut`, `csvjoin`, `csvgrep`, etc.

- For Amazon S3, [`s3cmd`](https://github.com/s3tools/s3cmd) is convenient and [`s4cmd`](https://github.com/bloomreach/s4cmd) is faster. Amazon's [`aws`](https://github.com/aws/aws-cli) and the improved [`saws`](https://github.com/donnemartin/saws) are essential for other AWS-related tasks.

- Know about `sort` and `uniq`, including uniq's `-u` and `-d` options -- see one-liners below. See also `comm`.

- Know about `cut`, `paste`, and `join` to manipulate text files. Many people use `cut` but forget about `join`.

- Know about `wc` to count newlines (`-l`), characters (`-m`), words (`-w`) and bytes (`-c`).

- Know about `tee` to copy from stdin to a file and also to stdout, as in `ls -al | tee file.txt`.

- For more complex calculations, including grouping, reversing fields, and statistical calculations, consider [`datamash`](https://www.gnu.org/software/datamash/).

## Network

### Check DNS
```sh
host localhost    # return IP

# localhost has address 127.0.0.1
# localhost has IPv6 address ::1
```

### Check PORT
```bash
telnet 192.168.0.1 3306
```

### Copy file localhost to remote-machine
##### download: remote -> local
```sh
scp user@remote_host:remote_file local_file
```

#### upload: local -> remote
```sh
scp local_file user@remote_host:remote_file
```

##### Example

```sh
scp lojas_xxx.csv brunorozza@yarn.systems.com:/home/brunorozza
lojas_xxx.csv
```

#### Check acess
- DNS lookup utility
```bash
dig my-addr-aws.net

# return SUCCESS
#
# ; <<>> DiG 9.11.5-P1-1ubuntu2.4-Ubuntu <<>> my-addr-aws.net
# ;; global options: +cmd
# ;; Got answer:
# ;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 10448
# ;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

# ;; OPT PSEUDOSECTION:
# ; EDNS: version: 0, flags:; udp: 65494
# ;; QUESTION SECTION:
# ;my-addr-aws.net.			IN	A

# ;; ANSWER SECTION:
# my-addr-aws.net.		43200	IN	A	150.162.2.10
...
```

--- 

## Check Linux Version
- Kernel
```bash
uname --all

# Linux avell 5.4.0-40-generic #44-Ubuntu SMP Tue Jun 23 00:01:04 UTC 2020 x86_64 x86_64 x86_64 GNU/Linux
```

- Operational System
```bash
cat /etc/*release

# DISTRIB_ID=Ubuntu
# DISTRIB_RELEASE=20.04
# DISTRIB_CODENAME=focal
# DISTRIB_DESCRIPTION="Ubuntu 20.04 LTS"
# NAME="Ubuntu"
# VERSION="20.04 LTS (Focal Fossa)"
# ID=ubuntu
# ID_LIKE=debian
# PRETTY_NAME="Ubuntu 20.04 LTS"
# VERSION_ID="20.04"
# HOME_URL="https://www.ubuntu.com/"
# SUPPORT_URL="https://help.ubuntu.com/"
# BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
# PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
# VERSION_CODENAME=focal
# UBUNTU_CODENAME=focal
```

### Generate Key
```bash
`< /dev/urandom tr -dc _A-Z-a-z-0-9 | head -c${1:-10};`
```
## Images in Markdown
- My theme: Material Filled
- Site: https://icons8.com.br/icons/material


- Responsive Images
Use `height=auto`

```
<img src="images/git_logo.png" align="right" height=auto width=30%/>
```

- align
`align=left`

<img src="images/devops.png" align="left" height=auto width=30%/>

<img src="images/devops.png" align="middle" height=auto width=30%/>

<img src="images/devops.png" align="right" height=auto width=30%/>

Line Test ...

---

# Virtualization

<img src="images/2-vm-vs-container-vs-serverless.png" align="center" height=auto width=100%/>


## Containers
Containers provide a consistent, isolated execution environment for applications.

The application and all its dependencies is packaged into a "container" and then a standard runtime environment is used to execute the app. This allows the container to start up in just a few seconds, because there's no OS to boot and initialize. You only need the app to launch.


The portability of the container makes it easy for applications to be deployed in multiple environments, either on-premises or in the cloud, often with no changes to the application.


- Docker Hub – para armazenamento público de “Docker Images”;
- Docker Registry – para armazenar imagens em ambiente on-premises;
- Docker Cloud – um serviço gerenciado para criar e executar contêiner;

#### Uninstall old versions
```
sudo apt remove docker docker-engine docker.io
```

The content of */var/lib/docker*, including images, containers, volumes and networks are preserved.


```
sudo ls /var/lib/docker
```


#### Docker Comands
- Run container: 
```
docker run [OPTIONS] CONTAINER [CONTAINER...]

# docker run -it -p 8888:8888 image:version
```

- Stop container: 
```
docker stop [OPTIONS] CONTAINER [CONTAINER...]
```

- Open terminal inside docker : 
```
docker exec -it --user root <DOCKER_NAME> /bin/bash
```

- Principal docker comands: 
```
docker images  # images
docker ps      # containers
docker volume  # volumes
docker network # network

nmap -n -p- localhost # show port in use
```


problemas git clone: usando você não é capaz de puxar commit específico com facilidade num CI
é melhor para testar o código e por em produção usar o COPY
Clone repository
```
CMD git clone <url-repo>
```

**References:**<br/>
- Documentation: https://docs.docker.com/engine/reference/commandline/docker/
- https://www.digitalocean.com/community/tutorials/how-to-remove-docker-images-containers-and-volumes



#### serverless computing
Serverless computing lets you run application code without creating, configuring, or maintaining a server. 

The core idea is that your application is broken into separate functions that run when triggered by some action

for example, you can build a serverless process that automatically sends an email confirmation after a customer makes an online purchase.

---

### Orchestrators

#### Mesos (Cluster resource manager)
É um orquestrador de containers assim como kubernetes ou Docker Swarm
    - Vantagens:  a orientação a microsserviços, grande volume de dados, análise em tempo real e dimensionamento elástico.
    - Simplificar a alocação de recursos, proporcionando uma aplicação coerente e experiência operacional através de nuvens privadas ou públicas;
    - Manter diversas tarefas de projeto na mesma infraestrutura como: analytics, microsserviços, monitoração, dados distribuídos e até aplicações (tentando melhorar a utilização e reduzir os custos);

#### Marathon
A manager for Mesos, with a nice user interface to start/monitor apps)

**References:**<br/>
https://www.infoq.com/br/presentations/infraestrutura-e-criacao-de-apis-em-alta-escala-usando-docker-e-apache-mesos?utm_source=infoq&utm_medium=related_content_link&utm_campaign=relatedContent_undefined_clk#downloadPdf

---


## Cloud
some of the features of cloud computing

### cost-effective
### scalable
### elastic
### Diference between scalable and elastic


- AWS
  - Configuration AWS
- Azure
  - [Sample Scripts](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/cli-samples?toc=%2Fcli%2Fazure%2Ftoc.json&bc=%2Fcli%2Fazure%2Fbreadcrumb%2Ftoc.json&view=azure-cli-latest)
  - https://kylenunery.com/guide-to-naming-things-in-azure/

### Configuration AWS

##### Install client aws
```bash
pip install awscli
```

##### Configure AWS CLI
```bash
aws configure

AWS Access Key ID [None]: KKKKKKKKKKKKKKKKK
AWS Secret Access Key [None]: KKKKKKKKKKKKK
Default region name [None]:
Default output format [None]: json
```

##### Test
```bash
aws s3 ls
```

### Configuration AZURE

##### Install CLI Azure
- https://docs.microsoft.com/en-us/cli/azure/install-azure-cli-apt?view=azure-cli-latest

- [Running on vs code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.azurecli) 

```bash
sudo apt-get update
sudo apt-get install ca-certificates curl apt-transport-https lsb-release gnupg

curl -sL https://packages.microsoft.com/keys/microsoft.asc | \
    gpg --dearmor | \
    sudo tee /etc/apt/trusted.gpg.d/microsoft.asc.gpg > /dev/null

```

- Add repository
```bash
AZ_REPO=$(lsb_release -cs)
echo "deb [arch=amd64] https://packages.microsoft.com/repos/azure-cli/ $AZ_REPO main" | \
    sudo tee /etc/apt/sources.list.d/azure-cli.list
```

- Update repository information and install package
```bash
sudo apt-get update
sudo apt-get install azure-cli
```

---

### S3
- Buckets or database _key-value_
- Policy of storage:
    - **Standard:** armazenamento de objetos com altos níveis de resiliência, disponibilidade e performance para dados acessados com frequência.
    - **Glacier:** custo extremamente baixo

- Protocol s3a


#### Access Buckets with AWS-cli
- `aws s3`
```bash
aws s3 ls s3://directory/sub-directory/
```

```bash
aws s3 cp /home/bruno/papyrus/gerar-dump/tmp/ s3://testes-bruno/ --recursive
```

- `s3cmd`

```bash
aws s3 cp /home/bruno/papyrus/gerar-dump-clients-s3/tmp/ s3://giancarlo/testes-bruno/ --recursive
```

- `s4cmd`

```bash
s4cmd ls s3://dumps/hourly/busca/2015/05/33/*/* | cut -d'/' -f10 | sort | uniq | wc -l
```

```bash
s4cmd put /home/bruno/papyrus/gerar-dump-clients-s3/tmp/* s3://giancarlo/testes-bruno/

# Copy file localhost to remote-bucket
```


### EC2 
...


### Route 53
Create route intern in DNS. Help transparent IP by users with uses.

- create in hosted zones intern `my-addr.aws.net`
- Next step click in `create record set`
- Test<br/>
```bash
dig my-addr.aws.net

# return
# ; <<>> DiG 9.10.3-P4-Ubuntu <<>> my-addr.aws.net
# ;; global options: +cmd
# ;; Got answer:
# ;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 42012
# ;; flags: qr rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 1

# ;; OPT PSEUDOSECTION:
# ; EDNS: version: 0, flags:; udp: 4096
# ;; QUESTION SECTION:
# ;my-addr.aws.net IN	A

# ;; ANSWER SECTION:
# my-addr.aws.net 60	IN  CNAME   mysqldatabasename.blabla.us-east-1.rds.amazonaws.com.
# mysqldatabasename.blabla.us-east-1.rds.amazonaws.com. 5 IN A 172.28.157.98
```


## Security
...

### VPC
É uma rede virtual privada (similar a uma VLAN). Usado para executar serviços aws isolados.

### Security Group
...

---

# Continuos Integration and Continuous Delivery 

- Crontab
- Jenkins
- Rundeck

**References:**<br/>
- https://github.com/jlevy/the-art-of-command-line/blob/master/README.md

---

<p  align="left">
<br/>
<a href="mailto:brunocampos01@gmail.com" target="_blank"><img src="https://img.icons8.com/material/48/000000/gmail--v1.png" alt="Gmail" width="30">
</a>
<a href="https://stackoverflow.com/users/8329698/bruno-campos" target="_blank"><img src="https://img.icons8.com/material/48/000000/stackoverflow.png" alt="GitHub" width="30">
</a>
<a href="https://www.linkedin.com/in/brunocampos01" target="_blank"><img src="https://img.icons8.com/windows/48/000000/linkedin.png" alt="LinkedIn" width="30"></a>
<a href="https://github.com/brunocampos01" target="_blank"><img src="https://img.icons8.com/material-outlined/48/000000/github.png" alt="GitHub" width="30"></a>
<a href="https://brunocampos01.netlify.app/" target="_blank"><img src="https://img.icons8.com/material/48/000000/web.png" alt="Website" width="30">
</a>
<a href="https://medium.com/@brunocampos01" target="_blank"><img src="https://img.icons8.com/material/48/000000/medium.png" alt="GitHub" width="30">
</a>
<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png",  align="right" /></a><br/>
</p>

