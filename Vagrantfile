Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/xenial64"
    
    config.vm.provision "shell", inline: <<-SHELL
       

 
    echo "-- Creamos el archivo datos_pacientes">/home/vagrant/datos_pacientes.sql
    
   SHELL
  end
