Vagrant.configure("2") do |config|
  # Usar una caja de Ubuntu
  config.vm.box = "ubuntu/bionic64"

  # Configuración de red
  config.vm.network "private_network", type: "dhcp"

  # Configuración de recursos
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "512"
    vb.cpus = 1
  end

  # Configuración para instalar Apache
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y apache2
    echo "¡Hola Mundo!" > /var/www/html/index.html
  SHELL

  # Compartir la carpeta local con el servidor web de Apache
  config.vm.synced_folder "./web_content", "/var/www/html"
end