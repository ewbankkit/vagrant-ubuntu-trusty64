# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box_check_update = false

  # vagrant plugin install vagrant-proxyconf
  if Vagrant.has_plugin?("vagrant-proxyconf")
    if ENV["http_proxy"]
      config.proxy.http = ENV["http_proxy"]
    else
      config.proxy.http = false
    end
    if ENV["https_proxy"]
      config.proxy.https = ENV["https_proxy"]
    else
      config.proxy.https = false
    end
    if ENV["no_proxy"]
      config.proxy.no_proxy = ENV["no_proxy"]
    else
      config.proxy.no_proxy = false
    end
  end

  config.vm.define "ubuntu-trusty64" do |e|
    # Download from Atlas.
    # Official Ubuntu Server 14.04 LTS (Trusty Tahr).
    e.vm.box         = "ubuntu/trusty64"
    e.vm.box_version = "20160822.0.2"

    e.vm.hostname = "ubuntu-trusty64"

    e.vm.provider "virtualbox" do |vb|
      vb.name = "ubuntu-trusty64"
      vb.customize ["modifyvm", :id, "--memory", "2048"]
      vb.customize ["modifyvm", :id, "--ioapic", "on"]
    end
  end
end
