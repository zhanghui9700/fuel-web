editable:
{
    "repo_setup": {
        "repos": {
            "type": "custom_repo_configuration",
            "description": "Please note: the first repository will be considered the operating system mirror that will be used during node provisioning.\nTo create a local repository mirror on the Fuel master node, please follow the instructions provided by running \"fuel-createmirror --help\" on the Fuel master node.\nPlease make sure your Fuel master node has Internet access to the repository before attempting to create a mirror.\n",
            "value": [
                {
                    "name": "ubuntu",
                    "section": "main universe multiverse",
                    "uri": "http://archive.ubuntu.com/ubuntu/",
                    "priority": null,
                    "suite": "trusty",
                    "type": "deb"
                },
                {
                    "name": "ubuntu-updates",
                    "section": "main universe multiverse",
                    "uri": "http://archive.ubuntu.com/ubuntu/",
                    "priority": null,
                    "suite": "trusty-updates",
                    "type": "deb"
                },
                {
                    "name": "ubuntu-security",
                    "section": "main universe multiverse",
                    "uri": "http://archive.ubuntu.com/ubuntu/",
                    "priority": null,
                    "suite": "trusty-security",
                    "type": "deb"
                },
                {
                    "name": "mos",
                    "section": "main restricted",
                    "uri": "http://10.20.0.2:8080/mitaka-9.0/ubuntu/x86_64",
                    "priority": 1050,
                    "suite": "mos9.0",
                    "type": "deb"
                },
                {
                    "name": "mos-updates",
                    "section": "main restricted",
                    "uri": "http://mirror.fuel-infra.org/mos-repos/ubuntu/9.0/",
                    "priority": 1050,
                    "suite": "mos9.0-updates",
                    "type": "deb"
                },
                {
                    "name": "mos-security",
                    "section": "main restricted",
                    "uri": "http://mirror.fuel-infra.org/mos-repos/ubuntu/9.0/",
                    "priority": 1050,
                    "suite": "mos9.0-security",
                    "type": "deb"
                },
                {
                    "name": "mos-holdback",
                    "section": "main restricted",
                    "uri": "http://mirror.fuel-infra.org/mos-repos/ubuntu/9.0/",
                    "priority": 1100,
                    "suite": "mos9.0-holdback",
                    "type": "deb"
                },
                {
                    "name": "Auxiliary",
                    "section": "main restricted",
                    "uri": "http://10.20.0.2:8080/mitaka-9.0/ubuntu/auxiliary",
                    "priority": 1150,
                    "suite": "auxiliary",
                    "type": "deb"
                }
            ],
            "extra_priority": null
        },
        "metadata": {
            "group": "general",
            "always_editable": true,
            "weight": 50,
            "label": "Repositories"
        }
    },
    "syslog": {
        "syslog_port": {
            "regex": {
                "source": "^([1-9][0-9]{0,3}|[1-5][0-9]{4}|6[0-4][0-9]{3}|65[0-4][0-9]{2}|655[0-2][0-9]|6553[0-5])$",
                "error": "Invalid syslog port"
            },
            "description": "Remote syslog port",
            "weight": 20,
            "value": "514",
            "label": "Port",
            "type": "text"
        },
        "syslog_transport": {
            "type": "radio",
            "values": [
                {
                    "data": "udp",
                    "description": "",
                    "label": "UDP"
                },
                {
                    "data": "tcp",
                    "description": "",
                    "label": "TCP"
                }
            ],
            "weight": 30,
            "value": "tcp",
            "label": "Syslog transport protocol"
        },
        "syslog_server": {
            "regex": {
                "source": "^[a-zA-Z\\d]+[-\\.\\da-zA-Z]*$",
                "error": "Invalid hostname"
            },
            "description": "Remote syslog hostname",
            "weight": 10,
            "value": "",
            "label": "Hostname",
            "type": "text"
        },
        "metadata": {
            "enabled": false,
            "group": "logging",
            "toggleable": true,
            "weight": 50,
            "label": "Syslog"
        }
    },
    "additional_components": {
        "ceilometer": {
            "weight": 60,
            "type": "checkbox",
            "description": "If selected, Ceilometer and Aodh components will be installed",
            "value": false,
            "label": "Install Ceilometer and Aodh"
        },
        "mongo": {
            "restrictions": [
                {
                    "settings:additional_components.ceilometer.value == false": "External Mongo aims to be an external backend for Ceilometer. Without Ceilometer enabled, External Mongo is useless and should not be installed."
                }
            ],
            "description": "If selected, You can use external Mongo DB as ceilometer backend",
            "weight": 70,
            "value": false,
            "label": "Use external Mongo DB",
            "type": "checkbox"
        },
        "heat": {
            "weight": 50,
            "type": "hidden",
            "description": "",
            "value": true,
            "label": ""
        },
        "murano-cfapi": {
            "restrictions": [
                {
                    "message": "Murano should be enabled",
                    "condition": "settings:additional_components.murano.value == false"
                },
                {
                    "action": "hide",
                    "condition": "not ('experimental' in version:feature_groups)"
                }
            ],
            "description": "If selected, Murano service broker will be installed",
            "weight": 30,
            "value": false,
            "label": "Install Murano service broker for Cloud Foundry",
            "type": "checkbox"
        },
        "murano": {
            "weight": 20,
            "type": "checkbox",
            "description": "If selected, Murano component will be installed",
            "value": false,
            "label": "Install Murano"
        },
        "sahara": {
            "weight": 10,
            "type": "checkbox",
            "description": "If selected, Sahara component will be installed",
            "value": false,
            "label": "Install Sahara"
        },
        "ironic": {
            "restrictions": [
                {
                    "cluster:net_provider != 'neutron' or networking_parameters:segmentation_type != 'vlan'": "Ironic requires Neutron with VLAN segmentation."
                },
                {
                    "settings:storage.images_ceph.value == true and settings:storage.objects_ceph.value == false": "Ironic requires Swift or RadosGW for Glance images."
                }
            ],
            "description": "If selected, Ironic component will be installed",
            "weight": 80,
            "value": false,
            "label": "Install Ironic",
            "type": "checkbox"
        },
        "metadata": {
            "group": "openstack_services",
            "weight": 10,
            "label": "Additional Components"
        }
    },
    "workloads_collector": {
        "password": {
            "type": "password",
            "value": "3Ee7uZ7MuS5yhDmDvkjh1Zh8"
        },
        "enabled": {
            "type": "hidden",
            "value": true
        },
        "user": {
            "type": "text",
            "value": "fuel_stats_user"
        },
        "tenant": {
            "type": "text",
            "value": "services"
        },
        "metadata": {
            "restrictions": [
                {
                    "action": "hide",
                    "condition": "true"
                }
            ],
            "group": "general",
            "weight": 10,
            "label": "Workloads Collector User"
        }
    },
    "provision": {
        "packages": {
            "type": "textarea",
            "weight": 10,
            "value": "acl\nanacron\nbash-completion\nbridge-utils\nbsdmainutils\nbuild-essential\ncloud-init\ncurl\ndaemonize\ndebconf-utils\ngdisk\ngrub-pc\nhpsa-dkms\nhwloc\ni40e-dkms\nlinux-firmware\nlinux-firmware-nonfree\nlinux-headers-generic-lts-trusty\nlinux-image-generic-lts-trusty\nlvm2\nmcollective\nmdadm\nmultipath-tools\nmultipath-tools-boot\nnailgun-agent\nnailgun-mcagents\nnetwork-checker\nntp\nopenssh-client\nopenssh-server\npuppet\npython-amqp\nruby-augeas\nruby-ipaddress\nruby-json\nruby-netaddr\nruby-openstack\nruby-shadow\nruby-stomp\nsystemd-shim\ntelnet\nubuntu-minimal\nubuntu-standard\nuuid-runtime\nvim\nvirt-what\nvlan\nxcloud-init\n",
            "label": "Initial packages"
        },
        "method": {
            "type": "hidden",
            "value": "image"
        },
        "metadata": {
            "restrictions": [
                {
                    "action": "hide",
                    "condition": "false"
                }
            ],
            "group": "general",
            "weight": 80,
            "label": "Provision"
        }
    },
    "neutron_advanced_configuration": {
        "neutron_qos": {
            "weight": 40,
            "type": "checkbox",
            "description": "Enable Neutron QoS advanced service plug-in",
            "value": false,
            "label": "Neutron QoS"
        },
        "neutron_l3_ha": {
            "restrictions": [
                {
                    "message": "Neutron DVR must be disabled in order to use Neutron L3 HA",
                    "condition": "settings:neutron_advanced_configuration.neutron_dvr.value == true"
                }
            ],
            "description": "Enable High Availability features for Virtual Routers in Neutron\nRequires at least 2 Controller nodes to function properly\n",
            "weight": 30,
            "value": false,
            "label": "Neutron L3 HA",
            "type": "checkbox"
        },
        "neutron_dvr": {
            "restrictions": [
                {
                    "networking_parameters:segmentation_type != 'vlan' and settings:neutron_advanced_configuration.neutron_l2_pop.value == false": "DVR requires L2 population to be enabled."
                }
            ],
            "description": "Enable Distributed Virtual Routers in Neutron",
            "weight": 20,
            "value": false,
            "label": "Neutron DVR",
            "type": "checkbox"
        },
        "neutron_l2_pop": {
            "restrictions": [
                {
                    "action": "hide",
                    "condition": "networking_parameters:segmentation_type == 'vlan'"
                }
            ],
            "description": "Enable L2 population mechanism in Neutron",
            "weight": 10,
            "value": false,
            "label": "Neutron L2 population",
            "type": "checkbox"
        },
        "metadata": {
            "restrictions": [
                {
                    "action": "hide",
                    "condition": "cluster:net_provider != 'neutron'"
                }
            ],
            "group": "network",
            "weight": 20,
            "label": "Neutron Advanced Configuration"
        }
    },
    "service_user": {
        "name": {
            "type": "hidden",
            "value": "fuel"
        },
        "sudo": {
            "type": "hidden",
            "value": "ALL=(ALL) NOPASSWD: ALL"
        },
        "homedir": {
            "type": "hidden",
            "value": "/var/lib/fuel"
        },
        "root_password": {
            "type": "hidden",
            "value": "r00tme"
        },
        "password": {
            "type": "hidden",
            "value": "hDEwC5vK3FAM2PjxqrdJ5Kb0"
        },
        "metadata": {
            "restrictions": [
                {
                    "action": "hide",
                    "condition": "true"
                }
            ],
            "group": "general",
            "weight": 10,
            "label": "Service user account"
        }
    },
    "operator_user": {
        "name": {
            "regex": {
                "source": "\\S",
                "error": "Empty username"
            },
            "description": "Username for operator user",
            "weight": 50,
            "value": "fueladmin",
            "label": "Username",
            "type": "text"
        },
        "sudo": {
            "value": "ALL=(ALL) NOPASSWD: ALL",
            "type": "textarea",
            "description": "Sudoers configuration directives for operator user, one per line.",
            "weight": 90,
            "label": "Sudoers configuration"
        },
        "homedir": {
            "regex": {
                "source": "^/\\S",
                "error": "Invalid path"
            },
            "description": "Home directory for operator user",
            "weight": 70,
            "value": "/home/fueladmin",
            "label": "Home directory",
            "type": "text"
        },
        "password": {
            "regex": {
                "source": "\\S",
                "error": "Empty password"
            },
            "description": "Password for operator user",
            "weight": 60,
            "value": "9q20j4PeelboytJ9z5kTcW8W",
            "label": "Password",
            "type": "password"
        },
        "authkeys": {
            "value": "",
            "type": "textarea",
            "description": "Public SSH keys to include to operator user's authorized keys, one per line.",
            "weight": 80,
            "label": "Authorized SSH keys"
        },
        "metadata": {
            "group": "general",
            "weight": 15,
            "label": "Operating System Access"
        }
    },
    "cgroups": {
        "metadata": {
            "restrictions": [
                {
                    "action": "hide",
                    "condition": "true"
                }
            ],
            "group": "general",
            "always_editable": true,
            "weight": 90,
            "label": "Cgroups conguration for services"
        }
    },
    "kernel_params": {
        "kernel": {
            "type": "text",
            "description": "Default kernel parameters",
            "value": "console=tty0 net.ifnames=1 biosdevname=0 rootdelay=90 nomodeset",
            "label": "Initial parameters"
        },
        "metadata": {
            "group": "general",
            "weight": 60,
            "label": "Kernel parameters"
        }
    },
    "storage": {
        "volumes_ceph": {
            "restrictions": [
                "settings:storage.volumes_lvm.value == true or settings:storage.volumes_block_device.value == true"
            ],
            "description": "Configures Cinder to store volumes in Ceph RBD images.",
            "weight": 20,
            "value": false,
            "label": "Ceph RBD for volumes (Cinder)",
            "type": "checkbox"
        },
        "objects_ceph": {
            "weight": 80,
            "type": "checkbox",
            "description": "Configures RadosGW front end for Ceph RBD. This exposes S3 and Swift API Interfaces. If enabled, this option will prevent Swift from installing.",
            "value": false,
            "label": "Ceph RadosGW for objects (Swift API)"
        },
        "auth_s3_keystone_ceph": {
            "restrictions": [
                {
                    "action": "hide",
                    "condition": "settings:storage.objects_ceph.value == false"
                }
            ],
            "description": "This allows to authenticate S3 requests basing on EC2/S3 credentials managed by Keystone. Please note that enabling the integration will increase the latency of S3 requests as well as load on Keystone service. Please consult with Mirantis Technical Bulletin 27 and Mirantis Support on mitigating the risks related with load.",
            "weight": 82,
            "value": false,
            "label": "Enable S3 API Authentication via Keystone in Ceph RadosGW",
            "type": "checkbox"
        },
        "volumes_lvm": {
            "restrictions": [
                "settings:storage.volumes_ceph.value == true"
            ],
            "description": "It is recommended to have at least one Cinder node.",
            "weight": 10,
            "value": true,
            "label": "Cinder LVM over iSCSI for volumes",
            "type": "checkbox"
        },
        "ephemeral_ceph": {
            "weight": 75,
            "type": "checkbox",
            "description": "Configures Nova to store ephemeral volumes in RBD. This works best if Ceph is enabled for volumes and images, too. Enables live migration of all types of Ceph backed VMs (without this option, live migration will only work with VMs launched from Cinder volumes).",
            "value": false,
            "label": "Ceph RBD for ephemeral volumes (Nova)"
        },
        "volumes_block_device": {
            "restrictions": [
                "settings:storage.volumes_ceph.value == true"
            ],
            "description": "High performance block device storage. It is recommended to have at least one Cinder Block Device",
            "weight": 15,
            "value": false,
            "label": "Cinder Block device driver",
            "type": "checkbox"
        },
        "mon_key": {
            "type": "hidden",
            "value": "AQA+uAJZAAAAABAApt7MhcuRbVRypFOk/Xmu2g=="
        },
        "bootstrap_osd_key": {
            "type": "hidden",
            "value": "AQA+uAJZAAAAABAAmUf1D3TPPYMKTpMbb3HsQA=="
        },
        "images_vcenter": {
            "restrictions": [
                {
                    "action": "hide",
                    "condition": "settings:common.use_vcenter.value != true"
                },
                {
                    "message": "Only one Glance backend could be selected.",
                    "condition": "settings:storage.images_ceph.value == true"
                }
            ],
            "description": "Configures Glance to use the vCenter/ESXi backend to store images. If enabled, this option will prevent Swift from installing.",
            "weight": 35,
            "value": false,
            "label": "VMware vCenter/ESXi datastore for images (Glance)",
            "type": "checkbox"
        },
        "osd_pool_size": {
            "regex": {
                "source": "^[1-9]\\d*$",
                "error": "Invalid number"
            },
            "description": "Configures the default number of object replicas in Ceph. This number must be equal to or lower than the number of deployed 'Ceph OSD' nodes.",
            "weight": 85,
            "value": "3",
            "label": "Ceph object replication factor",
            "type": "text"
        },
        "admin_key": {
            "type": "hidden",
            "value": "AQA+uAJZAAAAABAAbp0qUtuS/8sInG2CW5OGzg=="
        },
        "images_ceph": {
            "restrictions": [
                {
                    "settings:storage.images_vcenter.value == true": "Only one Glance backend could be selected."
                }
            ],
            "description": "Configures Glance to use the Ceph RBD backend to store images. If enabled, this option will prevent Swift from installing.",
            "weight": 30,
            "value": false,
            "label": "Ceph RBD for images (Glance)",
            "type": "checkbox"
        },
        "radosgw_key": {
            "type": "hidden",
            "value": "AQA+uAJZAAAAABAASYiav0Eyt0sgTsxqPppi5g=="
        },
        "fsid": {
            "type": "hidden",
            "value": "de123aba-9956-45ae-ad2e-bae734c39927"
        },
        "metadata": {
            "group": "storage",
            "weight": 60,
            "label": "Storage Backends"
        }
    },
    "public_ssl": {
        "hostname": {
            "regex": {
                "source": "^[a-zA-Z\\d]+[-\\.\\da-zA-Z]*$",
                "error": "Invalid DNS hostname"
            },
            "restrictions": [
                {
                    "action": "hide",
                    "condition": "settings:public_ssl.horizon.value == false and settings:public_ssl.services.value == false"
                }
            ],
            "description": "Your DNS entries should point to this name. Self-signed certificates also will use this hostname",
            "weight": 50,
            "value": "public.fuel.local",
            "label": "DNS hostname for public TLS endpoints",
            "type": "text"
        },
        "horizon": {
            "restrictions": [
                {
                    "settings:public_ssl.services.value == false": "TLS for OpenStack public endpoints should be enabled"
                }
            ],
            "description": "Secure access to Horizon enabling HTTPS instead of HTTP",
            "weight": 20,
            "value": false,
            "label": "HTTPS for Horizon",
            "type": "checkbox"
        },
        "services": {
            "weight": 10,
            "type": "checkbox",
            "description": "Enable TLS termination on HAProxy for OpenStack services",
            "value": false,
            "label": "TLS for OpenStack public endpoints"
        },
        "cert_data": {
            "restrictions": [
                {
                    "action": "hide",
                    "condition": "(settings:public_ssl.cert_source.value != 'user_uploaded') or (settings:public_ssl.horizon.value == false and settings:public_ssl.services.value == false)"
                }
            ],
            "description": "Certificate and private key data, concatenated into a single file",
            "weight": 40,
            "value": "",
            "label": "Certificate",
            "type": "file"
        },
        "cert_source": {
            "restrictions": [
                {
                    "action": "hide",
                    "condition": "settings:public_ssl.horizon.value == false and settings:public_ssl.services.value == false"
                }
            ],
            "description": "From where we'll get certificate and private key",
            "weight": 30,
            "value": "self_signed",
            "label": "Select source for certificate",
            "values": [
                {
                    "data": "self_signed",
                    "description": "Generate private key and certificate that will be signed by this key",
                    "label": "Self-signed"
                },
                {
                    "data": "user_uploaded",
                    "description": "Use pre-generated key and certificate",
                    "label": "I have my own keypair with certificate"
                }
            ],
            "type": "radio"
        },
        "metadata": {
            "group": "security",
            "weight": 110,
            "label": "Public TLS"
        }
    },
    "access": {
        "user": {
            "regex": {
                "source": "^(?!services$)(?!nova$)(?!glance$)(?!keystone$)(?!neutron$)(?!cinder$)(?!swift$)(?!ceph$)(?!ironic$)(?![Gg]uest$)(?!.* +.*$).+",
                "error": "Invalid username"
            },
            "description": "Username for Administrator",
            "weight": 10,
            "value": "admin",
            "label": "Username",
            "type": "text"
        },
        "password": {
            "regex": {
                "source": "\\S",
                "error": "Empty password"
            },
            "description": "Password for Administrator",
            "weight": 20,
            "value": "admin",
            "label": "Password",
            "type": "password"
        },
        "email": {
            "regex": {
                "source": "^\\S+@\\S+$",
                "error": "Invalid email"
            },
            "description": "Email address for Administrator",
            "weight": 40,
            "value": "admin@localhost",
            "label": "Email",
            "type": "text"
        },
        "tenant": {
            "regex": {
                "source": "^(?!services$)(?!nova$)(?!glance$)(?!keystone$)(?!neutron$)(?!cinder$)(?!swift$)(?!ceph$)(?!ironic$)(?![Gg]uest$)(?!.* +.*$).+",
                "error": "Invalid tenant name"
            },
            "description": "Tenant (project) name for Administrator",
            "weight": 30,
            "value": "admin",
            "label": "Tenant",
            "type": "text"
        },
        "metadata": {
            "group": "general",
            "weight": 10,
            "label": "OpenStack Access"
        }
    },
    "external_dns": {
        "dns_list": {
            "regex": {
                "source": "^(([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5])\\.){3}([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5])$",
                "error": "Invalid IP address"
            },
            "description": "List of upstream DNS servers",
            "weight": 10,
            "min": 0,
            "max": 3,
            "value": null,
            "label": "DNS list",
            "type": "text_list"
        },
        "metadata": {
            "group": "network",
            "weight": 30,
            "label": "Host OS DNS Servers"
        }
    },
    "murano_settings": {
        "murano_glance_artifacts_plugin": {
            "weight": 40,
            "type": "checkbox",
            "description": "If selected glance artifact repository will be enabled",
            "value": true,
            "label": "Enable glance artifact repository"
        },
        "murano_repo_url": {
            "weight": 10,
            "type": "text",
            "description": "",
            "value": "http://storage.apps.openstack.org/",
            "label": "Murano Repository URL"
        },
        "metadata": {
            "restrictions": [
                {
                    "action": "hide",
                    "message": "Murano is not enabled on the Additional Components section",
                    "condition": "settings:additional_components.murano.value == false"
                }
            ],
            "group": "openstack_services",
            "weight": 20,
            "label": "Murano Settings"
        }
    },
    "common": {
        "propagate_task_deploy": {
            "weight": 12,
            "type": "checkbox",
            "description": "Enables adaptation of granular tasks for task deployment.",
            "value": false,
            "label": "Propagate task based deployment."
        },
        "auto_assign_floating_ip": {
            "restrictions": [
                {
                    "action": "hide",
                    "condition": "cluster:net_provider == 'neutron'"
                }
            ],
            "group": "network",
            "description": "If selected, OpenStack will automatically assign a floating IP to a new instance",
            "weight": 40,
            "value": false,
            "label": "Auto assign floating IP",
            "type": "checkbox"
        },
        "use_cow_images": {
            "group": "storage",
            "description": "For most cases you will want qcow format. If it's disabled, raw image format will be used to run VMs. OpenStack with raw format currently does not support snapshotting.",
            "weight": 60,
            "value": true,
            "label": "Use qcow format for images",
            "type": "checkbox"
        },
        "auth_key": {
            "type": "hidden",
            "group": "security",
            "weight": 70,
            "value": ""
        },
        "puppet_debug": {
            "group": "logging",
            "description": "Debug puppet logging mode provides more information, but requires more disk space.",
            "weight": 20,
            "value": true,
            "label": "Puppet debug logging",
            "type": "checkbox"
        },
        "use_vcenter": {
            "type": "hidden",
            "weight": 30,
            "value": false
        },
        "libvirt_type": {
            "group": "compute",
            "weight": 30,
            "value": "kvm",
            "label": "Hypervisor type",
            "values": [
                {
                    "data": "kvm",
                    "description": "Choose this type of hypervisor if you run OpenStack on hardware",
                    "label": "KVM"
                },
                {
                    "data": "qemu",
                    "description": "Choose this type of hypervisor if you run OpenStack on virtual hosts.",
                    "label": "QEMU"
                }
            ],
            "type": "radio"
        },
        "resume_guests_state_on_host_boot": {
            "group": "compute",
            "description": "Whether to resume previous guests state when the host reboots. If enabled, this option causes guests assigned to the host to resume their previous state. If the guest was running a restart will be attempted when nova-compute starts. If the guest was not running previously, a restart will not be attempted.",
            "weight": 50,
            "value": true,
            "label": "Resume guests state on host boot",
            "type": "checkbox"
        },
        "debug": {
            "group": "logging",
            "description": "Debug logging mode provides more information, but requires more disk space.",
            "weight": 20,
            "value": false,
            "label": "OpenStack debug logging",
            "type": "checkbox"
        },
        "task_deploy": {
            "type": "hidden",
            "weight": 11,
            "value": true
        },
        "run_ping_checker": {
            "group": "network",
            "description": "Uncheck this box if the public gateway will not be available or will not respond to ICMP requests to the deployed cluster. If unchecked, the controllers will not take public gateway availability into account as part of the cluster health.  If the cluster will not have internet access, you will need to make sure to provide proper offline mirrors for the deployment to succeed.",
            "weight": 50,
            "value": true,
            "label": "Public Gateway is Available",
            "type": "checkbox"
        },
        "nova_quota": {
            "group": "compute",
            "description": "Quotas are used to limit CPU and memory usage for tenants. Enabling quotas will increase load on the Nova database.",
            "weight": 30,
            "value": false,
            "label": "Nova quotas",
            "type": "checkbox"
        },
        "security_groups": {
            "group": "security",
            "weight": 20,
            "value": "iptables_hybrid",
            "label": "Security Groups",
            "values": [
                {
                    "data": "openvswitch",
                    "description": "Choose this driver for OVS based security groups implementation. NOTE: Open vSwitch Firewall Driver requires kernel version >= 4.3 for non-dpdk case.",
                    "label": "Open vSwitch Firewall Driver"
                },
                {
                    "data": "iptables_hybrid",
                    "description": "Choose this driver for iptables/linux bridge based security groups implementation.",
                    "label": "Iptables-based Firewall Driver (No firewall for DPDK case)"
                }
            ],
            "type": "radio"
        },
        "metadata": {
            "weight": 10,
            "label": "Common"
        }
    },
    "external_mongo": {
        "mongo_db_name": {
            "regex": {
                "source": "^\\w+$",
                "error": "Invalid database name"
            },
            "description": "Mongo database name",
            "weight": 30,
            "value": "ceilometer",
            "label": "Database name",
            "type": "text"
        },
        "mongo_replset": {
            "weight": 30,
            "type": "text",
            "description": "Name for Mongo replication set",
            "value": "",
            "label": "Replset"
        },
        "mongo_user": {
            "regex": {
                "source": "^\\w+$",
                "error": "Empty username"
            },
            "description": "Mongo database username",
            "weight": 30,
            "value": "ceilometer",
            "label": "Username",
            "type": "text"
        },
        "hosts_ip": {
            "regex": {
                "source": "^(((25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\\.){3}(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?),)*((25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\\.){3}(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)$",
                "error": "Invalid hosts ip sequence"
            },
            "description": "IP Addresses of MongoDB. Use comma to split IPs",
            "weight": 30,
            "value": "",
            "label": "MongoDB hosts IP",
            "type": "text"
        },
        "mongo_password": {
            "regex": {
                "source": "^\\S*$",
                "error": "Password contains spaces"
            },
            "description": "Mongo database password",
            "weight": 30,
            "value": "ceilometer",
            "label": "Password",
            "type": "password"
        },
        "metadata": {
            "restrictions": [
                {
                    "action": "hide",
                    "message": "Ceilometer and MongoDB are not enabled on the Additional Components section",
                    "condition": "settings:additional_components.mongo.value == false"
                }
            ],
            "group": "openstack_services",
            "weight": 30,
            "label": "External MongoDB"
        }
    },
    "public_network_assignment": {
        "assign_to_all_nodes": {
            "weight": 10,
            "type": "checkbox",
            "description": "When disabled, public network will be assigned to controllers only",
            "value": false,
            "label": "Assign public network to all nodes"
        },
        "metadata": {
            "restrictions": [
                {
                    "action": "hide",
                    "condition": "cluster:net_provider != 'neutron'"
                }
            ],
            "group": "network",
            "weight": 10,
            "label": "Public network assignment"
        }
    },
    "external_ntp": {
        "ntp_list": {
            "regex": {
                "source": "^[a-zA-Z\\d]+[-\\.\\da-zA-Z]*$",
                "error": "Invalid NTP server"
            },
            "description": "List of upstream NTP servers",
            "weight": 10,
            "min": 1,
            "value": [
                "0.fuel.pool.ntp.org",
                "1.fuel.pool.ntp.org",
                "2.fuel.pool.ntp.org"
            ],
            "label": "NTP server list",
            "type": "text_list"
        },
        "metadata": {
            "group": "network",
            "weight": 40,
            "label": "Host OS NTP Servers"
        }
    },
    "corosync": {
        "verified": {
            "weight": 10,
            "type": "checkbox",
            "description": "Set True only if multicast is configured correctly on router.",
            "value": false,
            "label": "Need to pass network verification."
        },
        "group": {
            "weight": 10,
            "type": "text",
            "description": "",
            "value": "226.94.1.1",
            "label": "Group"
        },
        "port": {
            "weight": 20,
            "type": "text",
            "description": "",
            "value": "12000",
            "label": "Port"
        },
        "metadata": {
            "restrictions": [
                {
                    "action": "hide",
                    "condition": "true"
                }
            ],
            "group": "general",
            "weight": 50,
            "label": "Corosync"
        }
    }
}

generated:

{
    "glance_glare": {
        "user_password": "Qxv2ITExQZshZtgTf5sGH0jD"
    },
    "repo_setup": {
        "installer_kernel": {
            "local": "/var/www/nailgun/ubuntu/x86_64/images/linux",
            "remote_relative": "dists/trusty/main/installer-amd64/current/images/netboot/ubuntu-installer/amd64/linux"
        },
        "installer_initrd": {
            "local": "/var/www/nailgun/ubuntu/x86_64/images/initrd.gz",
            "remote_relative": "dists/trusty/main/installer-amd64/current/images/netboot/ubuntu-installer/amd64/initrd.gz"
        }
    },
    "murano-cfapi": {
        "db_password": "wv0gi7oOmcaf2Ckma4HLJX5L",
        "user_password": "MKakPrUHJkQdmYuycpNIqRBS",
        "rabbit_password": "xK1uayOY6eWq9huAwJ3WEXeF"
    },
    "heat": {
        "db_password": "4WzfoHZdjW7YLtUvYY1z6fsU",
        "user_password": "v05jnvd9pQHVt1pufEhLWkFs",
        "auth_encryption_key": "754ce969bb3a3f5c7d208cce18655cdc",
        "rabbit_password": "LVzQQM48AxY65m86l0fG1wwk"
    },
    "puppet": {
        "modules": "rsync://10.20.0.2:/puppet/mitaka-9.0/modules/",
        "manifests": "rsync://10.20.0.2:/puppet/mitaka-9.0/manifests/"
    },
    "rabbit": {
        "password": "C0xPfRUuDI6Zx7xICwth8dkW"
    },
    "mysql": {
        "root_password": "dG9TwqNWB3y4iLUWWZGxBbKI",
        "wsrep_password": "cXpzUQ0IYjuDA44MFnlA4TM4"
    },
    "ironic": {
        "swift_tempurl_key": "yQ8wLkGKwmZ3TVZZul0IL6ca",
        "db_password": "RL6LqSDeb3eCWlJ2iTfL0l6o",
        "user_password": "XnNHZfQoK3ECDTkCeaRo56i3"
    },
    "glance": {
        "db_password": "XVyVtsbNI6iAtfzFblvu91Tz",
        "user_password": "ym4tpW1WUqvgYTvXWJT4kNYb"
    },
    "cinder": {
        "db_password": "C2QsaX7mybOsScjnP84yB0o6",
        "user_password": "3rVZf2gQNwN14aP9jATCAQlA",
        "fixed_key": "dc98130bd65d926c6c6d76408e1607bc871b6f23f4cbbe70bde0ee2da1bba647"
    },
    "provision": {
        "image_data": {
            "/boot": {
                "container": "gzip",
                "uri": "http://10.20.0.2:8080/targetimages/env_1_ubuntu_1404_amd64-boot.img.gz",
                "format": "ext2"
            },
            "/": {
                "container": "gzip",
                "uri": "http://10.20.0.2:8080/targetimages/env_1_ubuntu_1404_amd64.img.gz",
                "format": "ext4"
            }
        },
        "codename": "trusty"
    },
    "quantum_settings": {
        "database": {
            "passwd": "tUdZnWImSt0BKUSeMRJB05os"
        },
        "keystone": {
            "admin_password": "NZy11l1QLWs6QXtFMNpHpzMZ"
        },
        "metadata": {
            "metadata_proxy_shared_secret": "BBe6zzRryHjhrxwZKgTFgMW1"
        }
    },
    "base_syslog": {
        "syslog_port": "514",
        "syslog_server": "10.20.0.2"
    },
    "ceilometer": {
        "db_password": "8tEYmdeKgsN3Atwk5idQonY0",
        "user_password": "DxBTOrMG0RT6gfgkAiWAWXdn",
        "metering_secret": "QargkI39hic5U5lWZ0zPlSSU"
    },
    "swift": {
        "user_password": "Ox5NysYCAB6jBAjmiLrflpiB"
    },
    "aodh": {
        "db_password": "QAKwUwho9BHYfTMyfOG2WnyZ",
        "user_password": "xz8gSdAkeIe7djhGN1BOr0gn"
    },
    "cobbler": {
        "profile": "ubuntu_1404_x86_64"
    },
    "nova": {
        "db_password": "1notRv9WqAyTCsKIx4KoZ6Z7",
        "user_password": "uiAW7tFP1TmUKwSc9rZn5UPh",
        "state_path": "/var/lib/nova"
    },
    "deployed_before": {
        "value": false
    },
    "murano": {
        "db_password": "P6tvepoN0mfniuQhxl7KQiHy",
        "user_password": "Y8EL8pIzCvmpBq64bHn6lMoQ",
        "rabbit_password": "Zk1IKuOinV83zz9YlLiJ0Yx5"
    },
    "keystone": {
        "db_password": "jOkp5667FUNSH4XCbtUSOl7a",
        "admin_token": "wbbKYog35s0tBi0f9aiFlbvQ"
    },
    "horizon": {
        "secret_key": "e8555623051accac68498e324b81c2ec15d21698f24d7796e20f6bc8815f9422"
    },
    "sahara": {
        "db_password": "vhJ5wvhJBPwnIFMJBBkLtAc8",
        "user_password": "p2eoH89EjeUAA2IY8kUqLEoV"
    }
}