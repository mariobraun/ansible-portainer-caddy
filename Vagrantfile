# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.hostname = "vagrant-ansible-portainer-caddy-ubuntu2204"
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "generic/ubuntu2204"

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine and only allow access
  # via 127.0.0.1 to disable public access
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Disable the default share of the current code directory. Doing this
  # provides improved isolation between the vagrant box and your host
  # by making sure your Vagrantfile isn't accessable to the vagrant box.
  # If you use this you may want to enable additional shared subfolders as
  # shown above.
  # config.vm.synced_folder ".", "/vagrant", disabled: true

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  # config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
  #   vb.memory = "1024"
  # end
  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Enable provisioning with a shell script. Additional provisioners such as
  # Ansible, Chef, Docker, Puppet and Salt are also available. Please see the
  # documentation for more information about their specific syntax and use.
  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL
#
  #  Provider (esxi) settings
  #
  config.vm.provider :vmware_esxi do |esxi|

    #  REQUIRED!  ESXi hostname/IP
    esxi.esxi_hostname = '192.168.1.10'

    #  ESXi username
   esxi.esxi_username = 'root'

    #  IMPORTANT!  Set ESXi password.
    #    1) 'prompt:'
    #    2) 'file:'  or  'file:my_secret_file'
    #    3) 'env:'  or 'env:my_secret_env_var'
    #    4) 'key:'  or  key:~/.ssh/some_ssh_private_key'
    #    5) or esxi.esxi_password = 'my_esxi_password'
    #
    esxi.esxi_password = 'prompt:'

    #  SSH port.
    #esxi.esxi_hostport = 22

    #  HIGHLY RECOMMENDED!  ESXi Virtual Network
    #    You should specify an ESXi Virtual Network!  If it's not specified, the
    #    default is to use the first found.  You can specify up to 10 virtual
    #    networks using an array format.
    esxi.esxi_virtual_network = ['VM Network']

    #  OPTIONAL.  Specify a Disk Store
    esxi.esxi_disk_store = 'esx03--VMs--1TB-Crucial'

    #  OPTIONAL.  Resource Pool
    #     Vagrant will NOT create a Resource pool it for you.
    #esxi.esxi_resource_pool = '/Vagrant'

    #  Optional. Specify a VM to clone instead of uploading a box.
    #    Vagrant can use any stopped VM as the source 'box'.   The VM must be
    #    registered, stopped and must have the vagrant insecure ssh key installed.
    #    If the VM is stored in a resource pool, it must be specified.
    #    See wiki: https://github.com/josenk/vagrant-vmware-esxi/wiki/How-to-clone_from_vm
    #esxi.clone_from_vm = 'resource_pool/source_vm'

    #  OPTIONAL.  Guest VM name to use.
    #    The Default will be automatically generated.
    esxi.guest_name = 'vagrant-ansible-portainer-caddy-ubuntu2204'

    #  OPTIONAL.  When automatically naming VMs, use this prefix.
    #esxi.guest_name_prefix = 'V-'

    #  OPTIONAL.  Set the guest username login.  The default is 'vagrant'.
    #esxi.guest_username = 'vagrant'

    #  OPTIONAL.  Memory size override
    esxi.guest_memsize = '8192'

    #  OPTIONAL.  Virtual CPUs override
    esxi.guest_numvcpus = '4'

    #  OPTIONAL & RISKY.  Specify up to 10 MAC addresses
    #    The default is ovftool to automatically generate a MAC address.
    #    You can specify an array of MAC addresses using upper or lower case,
    #    separated by colons ':'.
    #esxi.guest_mac_address = ['00:50:56:aa:bb:cc', '00:50:56:01:01:01','00:50:56:02:02:02','00:50:56:BE:AF:01' ]

    #   OPTIONAL & RISKY.  Specify a guest_nic_type
    #     The validated list of guest_nic_types are 'e1000', 'e1000e', 'vmxnet',
    #     'vmxnet2', 'vmxnet3', 'Vlance', and 'Flexible'.
    #esxi.guest_nic_type = 'e1000'

    #  OPTIONAL. Specify a disk type.
    #    If unspecified, it will be set to 'thin'.  Otherwise, you can set to
    #    'thin', 'thick', or 'eagerzeroedthick'
    #esxi.guest_disk_type = 'thick'

    #  OPTIONAL. Boot disk size.
    #    If unspecified, the boot disk size will be the same as the original
    #    box.  You can specify a larger boot disk size in GB.  The extra disk space
    #    will NOT automatically be available to your OS.  You will need to
    #    create or modify partitions, LVM and/or filesystems.
    #esxi.guest_boot_disk_size = 50

    #  OPTIONAL.  Create additional storage for guests.
    #    You can specify an array of up to 13 virtual disk sizes (in GB) that you
    #    would like the provider to create once the guest has been created.  You
    #    can optionally specify the size and datastore using a hash.
    #esxi.guest_storage = [ 10, 20, { size: 30, datastore: 'datastore1' } ]

    #  OPTIONAL. specify snapshot options.
    #esxi.guest_snapshot_includememory = 'true'
    #esxi.guest_snapshot_quiesced = 'true'

    #  RISKY. guest_guestos
    #    https://github.com/josenk/vagrant-vmware-esxi/wiki/VMware-ESXi-6.5-guestOS-types
    #esxi.guest_guestos = 'centos-64'

    #  OPTIONAL. guest_virtualhw_version
    #    ESXi 6.7 supports these versions. 4,7,8,9,10,11,12,13 & 14.
    #esxi.guest_virtualhw_version = '9'

    #  OPTIONAL. Guest Autostart
    #    Guest VM will autostart when esxi host is booted. 'true' or 'false'(default)
    #esxi.guest_autostart = 'false'

    #  RISKY. guest_custom_vmx_settings
    #esxi.guest_custom_vmx_settings = [['vhv.enable','TRUE'], ['floppy0.present','TRUE']]

    #  OPTIONAL. local_lax
    #esxi.local_lax = 'true'

    #  OPTIONAL. Guest IP Caching
    #esxi.local_use_ip_cache = 'True'

    #  DANGEROUS!  Allow Overwrite
    #    If unspecified, the default is to produce an error if overwriting
    #    VMs and packages.
    #esxi.local_allow_overwrite = 'True'

    #  Advanced Users.
    #    If set to 'True', all WARNINGS will produce a FAILURE and Vagrant will stop.
    #esxi.local_failonwarning = 'True'

    #  Plugin debug output.
    #    Please send any bug reports with this debug output...
    #esxi.debug = 'true'

  end

end
