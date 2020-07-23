FROM centos:7

RUN yum install -y wget && \
wget -q -O - https://www.atomicorp.com/installers/atomic | sh && \
yum install -y java-11-openjdk ncrack git 

RUN rpm -vhU https://nmap.org/dist/nmap-7.80-1.x86_64.rpm

RUN echo -e 'export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-11.0.7.10-4.el7_8.x86_64 \nexport CLASSPATH=.:$JAVA_HOME/jre/lib/rt.jar:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar \nexport PATH=$PATH:$JAVA_HOME/bin' > /etc/profile


WORKDIR /tools
ADD quick_start.sh .

RUN source /etc/profile && bash quick_start.sh