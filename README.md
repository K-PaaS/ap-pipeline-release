## Related Repositories

<table>
  <tr>
    <td colspan=2 align=center>플랫폼</td>
    <td colspan=2 align=center><a href="https://github.com/K-PaaS/cp-deployment">컨테이너 플랫폼</a></td>
    <td colspan=2 align=center><a href="https://github.com/K-PaaS/sidecar-deployment">사이드카</a></td>
    <td colspan=2 align=center><a href="https://github.com/K-PaaS/ap-deployment">어플리케이션 플랫폼</a></td>
  </tr>
  <tr>
    <td colspan=2 align=center>포털</td>
    <td colspan=2 align=center><a href="https://github.com/K-PaaS/cp-portal-release">CP 포털</a></td>
    <td colspan=2 align=center>-</td>
    <td colspan=2 align=center><a href="https://github.com/K-PaaS/portal-deployment">AP 포털</a></td>
  </tr>
  <tr align=center>
    <td colspan=2 rowspan=9>Component<br>/ 서비스</td>
    <td colspan=2><a href="https://github.com/K-PaaS/cp-portal-common-api">Common API</a></td>
    <td colspan=2>-</td>
    <td colspan=2><a href="https://github.com/K-PaaS/ap-mongodb-shard-release">MongoDB</a></td>
  </tr>
  <tr align=center>
    <td colspan=2><a href="https://github.com/K-PaaS/cp-metrics-api">Metric API</a></td>
    <td colspan=2>  </td>
    <td colspan=2><a href="https://github.com/K-PaaS/ap-mysql-release">MySQL</a></td>
  </tr>
  <tr align=center>
    <td colspan=2><a href="https://github.com/K-PaaS/cp-portal-api">Portal API</a></td>
    <td colspan=2>  </td>
    <td colspan=2><a href="https://github.com/K-PaaS/ap-pipeline-release">🚩 Pipeline</a></td>
  </tr>
  <tr align=center>
    <td colspan=2><a href="https://github.com/K-PaaS/cp-portal-ui">Portal UI</a></td>
    <td colspan=2>  </td>
    <td colspan=2><a href="https://github.com/K-PaaS/ap-rabbitmq-release">RabbintMQ</a></td>
  </tr>
  <tr align=center>
    <td colspan=2><a href="https://github.com/K-PaaS/cp-portal-service-broker">Service Broker</a></td>
    <td colspan=2>  </td>
    <td colspan=2><a href="https://github.com/K-PaaS/ap-on-demand-redis-release">Redis</a></td>
  </tr>
  <tr align=center>
    <td colspan=2><a href="https://github.com/K-PaaS/cp-metrics-api">Terraman API</a></td>
    <td colspan=2>  </td>
    <td colspan=2><a href="https://github.com/K-PaaS/ap-source-control-release">SoureceControl</a></td>
  </tr>
</table>
<i>🚩 You are here.</i>

## Notice
#### 릴리즈의 경로가 https://nextcloud.paas-ta.org/ 에서 https://nextcloud.k-paas.org/ 로 변경되었습니다  




  

  


## ap-pipeline-release  

### Application Platform Delivery Pipeline Release Configuration  

  - haproxy : 1 machine  
  - ap-pipeline-ui : N machine(s)  
  - ap-pipeline-broker : 1 machine  
  - ap-pipeline-common-api : N machine(s)  
  - ap-pipeline-api : N machine(s)  
  - ap-pipeline-inspection-api : N machine(s)  
  - ap-pipeline-binary-storage-api : 1 machine  
  - ap-pipeline-scheduler : 1 machine  
  - ci_server : N machine(s)  
  - inspection : 1 machine  
  - binary_storage : 1 machine  
  - mariadb : 1 machine  
  - postgres : 1 machine  

### Create Application Platform Delivery Pipeline Release  
  - Download the latest Delivery Pipeline Release  
    ```   
    $ git clone https://github.com/K-PaaS/ap-pipeline-release.git
    $ cd ap-pipeline-release  
    ```  
  - Download & Copy "source files" into the src directory  
    ```  
    ## download source files
    $ wget -O src.zip https://nextcloud.k-paas.org/index.php/s/FeDg3MssjBgr334/download

    ## unzip download source files
    $ unzip src.zip  

    ## src directory
    src  
        ├── cf-cli  
        │   └── cf-cli_6.26.0_linux_x86-64.tgz  
        ├── ap-pipeline-api  
        │   └── ap-pipeline-api.war  
        ├── ap-pipeline-binary-storage-api  
        │   └── ap-pipeline-binary-storage-api.jar  
        ├── ap-pipeline-common-api  
        │   └── ap-pipeline-common-api-1.0.3.jar
        ├── ap-pipeline-inspection-api  
        │   └── ap-pipeline-inspection-api.jar  
        ├── ap-pipeline-scheduler  
        │   └── ap-pipeline-scheduler.jar  
        ├── ap-pipeline-broker  
        │   └── ap-pipeline-broker.jar  
        ├── ap-pipeline-ui  
        │   └── ap-pipeline-ui-1.0.4.war  
        ├── git  
        │   └── git-2.9.3.tar.gz  
        ├── gradle  
        │   ├── gradle-2.14.1-bin.zip  
        │   ├── gradle-3.5-bin.zip
        │   ├── gradle-4.10.3-bin.zip
        │   ├── gradle-5.6.4-bin.zip
        │   ├── gradle-6.7.1-bin.zip  
        │   └── gradle-7.3.3-bin.zip          
        ├── haproxy  
        │   └── haproxy-1.6.5.tar.gz  
        ├── java  
        │   └── server-jre-8u121-linux-x64.tar.gz  
        ├── jenkins  
        │   ├── jenkins.war  
        │   └── update_files_1.2.0.tar.gz  
        ├── mariadb  
        │   └── mariadb-10.5.17-linux-x86_64.tar.gz
        ├── maven  
        │   ├── apache-maven-3.5.0-bin.tar.gz          
        │   ├── apache-maven-3.6.3-bin.tar.gz                  
        │   └── apache-maven-3.8.4-bin.tar.gz  
        ├── openjdk
        │   ├── openjdk-11_linux-x64_bin.tar.gz
        │   └── openjdk-17_linux-x64_bin.tar.gz
        ├── postgres  
        │   └── postgresql-11.21.tar.gz
        ├── python  
        │   └── Python-3.6.9.tgz
        ├── sonarqube  
        │   └── sonarqube-5.6.7-K-PaaS.zip
        ├── sshpass  
        │   └── sshpass-1.06.tar.gz  
        └── swift-all-in-one  
            └── swift-2.31.1.tar.gz
    ```  
  - Create Application Platform Delivery Pipeline Release  
    ```  
    ## <VERSION> :: release version (e.g. 1.3.0)
    ## <RELEASE_TARBALL_PATH> :: release file path (e.g. /home/ubuntu/workspace/ap-pipeline-release-<VERSION>.tgz)
    $ bosh -e <bosh_name> create-release --name=ap-pipeline --version=<VERSION> --tarball=<RELEASE_TARBALL_PATH> --force
    ```  

### Deployment    
  - https://github.com/K-PaaS/service-deployment  


## Contributors ✨
<a href="https://github.com/K-PaaS/ap-pipeline-release/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=K-PaaS/ap-pipeline-release" />
</a>
