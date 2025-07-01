Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/jammy64"

  # Forward the server port
  config.vm.network "forwarded_port", guest: 5000, host: 5000

  # Provisioning script
  config.vm.provision "shell", inline: <<-SHELL
    # Update and install dependencies
    sudo apt-get update
    sudo apt-get install -y curl gnupg

    # Install Node.js (v18)
    curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
    sudo apt-get install -y nodejs

    # Optional: Install MongoDB CLI client
    wget -qO - https://pgp.mongodb.com/server-6.0.asc | sudo gpg --dearmor -o /usr/share/keyrings/mongodb-server-6.0.gpg
    echo "deb [ signed-by=/usr/share/keyrings/mongodb-server-6.0.gpg ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/6.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-6.0.list
    sudo apt-get update
    sudo apt-get install -y mongodb-org-shell

    # Go to shared folder (your project directory)
    cd /vagrant

    # Install project dependencies
    npm install

    # Run the app (ensure this doesn't block provisioning — run in background)
    nohup node server.js > app.log 2>&1 &
  SHELL
end