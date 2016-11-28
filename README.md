#ActiveMQ bosh release sample

##Howto create a bosh release log

```
   bosh status
   bosh stemcells

   bosh init release activemq
   bosh generate job activemq-server
   vi jobs/activemq-server/monit 
   vi jobs/activemq-server/templates/ctl.erb
   wget "http://www.apache.org/dyn/closer.cgi?filename=/activemq/5.14.1/apache-activemq-5.14.1-bin.tar.gz&action=download" -O apache-activemq-5.14.1-bin.tar.gz
   vi jobs/activemq-server/templates/ctl.erb
   vi jobs/activemq-server/monit 
   vi jobs/activemq-server/spec 

   bosh generate package openjdk
   bosh generate package activemq
   vi packages/activemq/spec 
   vi packages/activemq/spec 
   wget  https://download.run.pivotal.io/openjdk/trusty/x86_64/openjdk-1.8.0_101.tar.gz
   vi packages/activemq/spec 
   vi packages/openjdk/spec 
   vi packages/openjdk/packaging 
   vi packages/activemq/packaging 

   vi jobs/activemq-server/spec 
   vi jobs/activemq-server/spec 
   vi packages/activemq/spec 
   vi jobs/activemq-server/spec 

   mv activemq/apache-activemq-5.14.1.tar.gz /tmp/
   mv openjdk/openjdk-1.8.0_101.tar.gz /tmp/
   bosh add blob /tmp/openjdk-1.8.0_101.tar.gz openjdk
   bosh add blob /tmp/apache-activemq-5.14.1.tar.gz activemq

   bosh create release --name activemq --version 0.1 --force
   bosh upload release

   bosh create release --name activemq --version 0.2 --force

   bosh deployment manifest.yml
   bosh -n deploy
```
