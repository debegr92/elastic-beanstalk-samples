### https-instancecert-<platform>.config
Install a certificate and private key stored in Amazon S3, and configure the proxy server that runs in front of your application to terminate HTTPS connections. Use this configuration to terminate HTTPS in single instance environments, environments with a load balancer configured to pass through encrypted traffic as-is, or environments with a load balancer that decrypts HTTPS, then re-encrypts between the load balancer and the instance serving the request.

For single instance environments, include `https-singleinstance-securitygroup.config` as well to allow HTTPS traffic through the instance's security group.

### https-redirect-<platform>.config
Configure the proxy server that runs in front of your application to redirect HTTP requests on port 80 to the same path on HTTPS/443.

### https-singleinstance-securitygroup.config
Modify your instance's security group to allow HTTPS traffic on port 443. Use in conjunction with `https-instancecert-<platform>.config` to support HTTPS connections in a single instance environment.

### ssh-sourcerestriction.config
Use the `SSHSourceRestriction` option in the `aws:autoscaling:launchconfiguration` namespace to restrict SSH traffic to connections from instances in a security group that you control. By default, Elastic Beanstalk opens port 22 to the world when you assign a key pair to your instances. Use this configuration file to override that behavior.