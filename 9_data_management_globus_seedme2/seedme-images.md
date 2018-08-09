* [Download](https://www.docker.com/community-edition) and install Docker community edition for your operating system
    * Test if docker setup works on [linux](https://docs.docker.com/install/linux/docker-ce/ubuntu/#install-from-a-package) or [mac](https://docs.docker.com/docker-for-mac/#explore-the-application) or [windows](https://docs.docker.com/docker-for-windows/#explore-the-application)
+ [Download](https://dibbs.seedme.org/sites/dibbs.seedme.org/files/docker-images/seedme-workshop-2018-begin.tar.gz) begin docker image, this will be used to get started with the tutorial
+ [Download](https://dibbs.seedme.org/sites/dibbs.seedme.org/files/docker-images/seedme-workshop-2018-final.tar.gz) final docker image, this is a fully configured sandbox website 

# Import the docker images, then run seedme:begin and seedme:final containers
```bash
#import begin image as seedme:begin
docker import --change 'CMD ["apache2-foreground"]' seedme-workshop-2018-begin.tar.gz seedme:begin

#import final image as seedme:final
docker import --change 'CMD ["apache2-foreground"]' seedme-workshop-2018-begin.tar.gz seedme:final

# Create and start a new container for begin image
docker run -d --name begin -p 7000:80 seedme:begin
# Open your browser at localhost or 127.0.0.1:7000

# Create and start a new container for final image
docker run -d --name final -p 8000:80 seedme:final
# Open your browser at localhost or 127.0.0.1:8000
```
