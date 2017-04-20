> nailgun send task to astute, every task has a type, astute execute task by type.

    ORCHESTRATOR_TASK_TYPES = Enum(
        'puppet',
        'shell',
        'sync',
        'upload_file',
        'group',
        'stage',
        'skipped',
        'reboot',
        'copy_files',
        'role',
        'master_shell',
        'move_to_bootstrap',
        'erase_node'
    )

[
    {
        "args": {
            "task_uuid": "7761b01b-4e52-4000-9db4-e7078f468ab8",
            # provisioning_info --> ProvisioningSerializer90.serialize
            "provisioning_info": {
                # serialize_cluster
                "engine": {
                    "url": "http://10.20.0.2:80/cobbler_api",
                    "username": "cobbler",
                    "password": "8hOBmOlABdB4DDuX5XXhI0Sl",
                    "master_ip": "10.20.0.2"
                },
                # serialized_nodes
                "nodes": [
                    {
                        "profile": "ubuntu_1404_x86_64",
                        "name_servers_search": "\"domain.tld\"",
                        "uid": "4",
                        "interfaces": {
                            "eth3": {
                                "static": "0",
                                "mac_address": "52:54:00:66:d7:8e"
                            },
                            "eth2": {
                                "static": "0",
                                "mac_address": "52:54:00:56:0d:b1"
                            },
                            "eth1": {
                                "static": "0",
                                "mac_address": "52:54:00:4f:5a:5f"
                            },
                            "eth0": {
                                "ip_address": "10.20.0.3",
                                "dns_name": "node-4.domain.tld",
                                "netmask": "255.255.255.0",
                                "static": "0",
                                "mac_address": "52:54:00:16:ea:68"
                            }
                        },
                        "interfaces_extra": {
                            "eth3": {
                                "onboot": "no",
                                "peerdns": "no"
                            },
                            "eth2": {
                                "onboot": "no",
                                "peerdns": "no"
                            },
                            "eth1": {
                                "onboot": "no",
                                "peerdns": "no"
                            },
                            "eth0": {
                                "onboot": "yes",
                                "peerdns": "no"
                            }
                        },
                        "power_type": "ssh",
                        "power_user": "root",
                        "kernel_options": {
                            "udevrules": "52:54:00:16:ea:68_eth0,52:54:00:4f:5a:5f_eth1,52:54:00:56:0d:b1_eth2,52:54:00:66:d7:8e_eth3",
                            "netcfg/choose_interface": "52:54:00:16:ea:68"
                        },
                        "power_address": "10.20.0.3",
                        "name_servers": "\"10.20.0.2\"",
                        "ks_meta": {
                            "gw": "10.20.0.2",
                            "mco_enable": 1,
                            "mco_identity": 4,
                            "mco_user": "mcollective",
                            "install_log_2_syslog": 1,
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
                            "timezone": "Etc/UTC",
                            "puppet_master": "localhost",
                            "user_accounts": [
                                {
                                    "ssh_keys": [
                                        "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQD5dzcY/wMTG7TFwNV2fakO9B6fRy9BpTW9Va4TRN+3KHQgV/5ZYqdFRcqjQU5EqFQR50ThOrTVWjO6lbqINhSqOVKJ0wpUkdB5Fd+ovevSs+VywQbVW6RBU+YE34mlUgsZ+UJ5K4vAWV2IIp0FHikJ3ehr2FQMvJb9B+l3SpNw7hjKCOQ9KHBzofMnaq9QqZyvjRchd7zmIrJO+DV+MQDxZ4AqmQBzCVXjQK3RJ2a9ulBVw7ypQ1qyHm2JDtWxrCoEXDEGYAKrVMxHPWXKOpHtVe0+1trIN6uWtLyDRmHvma4ApiiLCJFQo42KigWz//MB+duHLosGgtEwBIFDWOZp root@xcloudos.domain.tld"
                                    ],
                                    "password": "9q20j4PeelboytJ9z5kTcW8W",
                                    "sudo": [
                                        "ALL=(ALL) NOPASSWD: ALL"
                                    ],
                                    "name": "fueladmin",
                                    "homedir": "/home/fueladmin"
                                },
                                {
                                    "ssh_keys": [
                                        "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQD5dzcY/wMTG7TFwNV2fakO9B6fRy9BpTW9Va4TRN+3KHQgV/5ZYqdFRcqjQU5EqFQR50ThOrTVWjO6lbqINhSqOVKJ0wpUkdB5Fd+ovevSs+VywQbVW6RBU+YE34mlUgsZ+UJ5K4vAWV2IIp0FHikJ3ehr2FQMvJb9B+l3SpNw7hjKCOQ9KHBzofMnaq9QqZyvjRchd7zmIrJO+DV+MQDxZ4AqmQBzCVXjQK3RJ2a9ulBVw7ypQ1qyHm2JDtWxrCoEXDEGYAKrVMxHPWXKOpHtVe0+1trIN6uWtLyDRmHvma4ApiiLCJFQo42KigWz//MB+duHLosGgtEwBIFDWOZp root@xcloudos.domain.tld"
                                    ],
                                    "password": "hDEwC5vK3FAM2PjxqrdJ5Kb0",
                                    "sudo": [
                                        "ALL=(ALL) NOPASSWD: ALL"
                                    ],
                                    "name": "fuel",
                                    "homedir": "/var/lib/fuel"
                                },
                                {
                                    "ssh_keys": [
                                        "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQD5dzcY/wMTG7TFwNV2fakO9B6fRy9BpTW9Va4TRN+3KHQgV/5ZYqdFRcqjQU5EqFQR50ThOrTVWjO6lbqINhSqOVKJ0wpUkdB5Fd+ovevSs+VywQbVW6RBU+YE34mlUgsZ+UJ5K4vAWV2IIp0FHikJ3ehr2FQMvJb9B+l3SpNw7hjKCOQ9KHBzofMnaq9QqZyvjRchd7zmIrJO+DV+MQDxZ4AqmQBzCVXjQK3RJ2a9ulBVw7ypQ1qyHm2JDtWxrCoEXDEGYAKrVMxHPWXKOpHtVe0+1trIN6uWtLyDRmHvma4ApiiLCJFQo42KigWz//MB+duHLosGgtEwBIFDWOZp root@xcloudos.domain.tld"
                                    ],
                                    "password": "r00tme",
                                    "name": "root",
                                    "homedir": "/root"
                                }
                            ],
                            "pm_data": {
                                "kernel_params": "console=tty0 net.ifnames=1 biosdevname=0 rootdelay=90 nomodeset",
                                "ks_spaces": [
                                    {
                                        "name": "vda",
                                        "extra": [],
                                        "bootable": true,
                                        "free_space": 81100,
                                        "volumes": [
                                            {
                                                "type": "boot",
                                                "size": 300
                                            },
                                            {
                                                "mount": "/boot",
                                                "type": "partition",
                                                "file_system": "ext2",
                                                "name": "Boot",
                                                "size": 200
                                            },
                                            {
                                                "type": "lvm_meta_pool",
                                                "size": 0
                                            },
                                            {
                                                "vg": "os",
                                                "type": "pv",
                                                "lvm_meta_size": 64,
                                                "size": 24640
                                            },
                                            {
                                                "vg": "logs",
                                                "type": "pv",
                                                "lvm_meta_size": 64,
                                                "size": 10304
                                            },
                                            {
                                                "vg": "mysql",
                                                "type": "pv",
                                                "lvm_meta_size": 64,
                                                "size": 20544
                                            },
                                            {
                                                "vg": "horizon",
                                                "type": "pv",
                                                "lvm_meta_size": 64,
                                                "size": 11328
                                            },
                                            {
                                                "vg": "image",
                                                "type": "pv",
                                                "lvm_meta_size": 64,
                                                "size": 14604
                                            }
                                        ],
                                        "type": "disk",
                                        "id": "vda",
                                        "size": 81920
                                    },
                                    {
                                        "_allocate_size": "min",
                                        "label": "Base System",
                                        "min_size": 24576,
                                        "volumes": [
                                            {
                                                "mount": "/",
                                                "type": "lv",
                                                "name": "root",
                                                "file_system": "ext4",
                                                "size": 16384
                                            },
                                            {
                                                "mount": "swap",
                                                "type": "lv",
                                                "name": "swap",
                                                "file_system": "swap",
                                                "size": 8192
                                            }
                                        ],
                                        "type": "vg",
                                        "id": "os"
                                    },
                                    {
                                        "_allocate_size": "min",
                                        "label": "Logs",
                                        "min_size": 10240,
                                        "volumes": [
                                            {
                                                "mount": "/var/log",
                                                "type": "lv",
                                                "name": "log",
                                                "file_system": "ext4",
                                                "size": 10240
                                            }
                                        ],
                                        "type": "vg",
                                        "id": "logs"
                                    },
                                    {
                                        "_allocate_size": "all",
                                        "label": "Image Storage",
                                        "min_size": 5120,
                                        "volumes": [
                                            {
                                                "mount": "/var/lib/glance",
                                                "type": "lv",
                                                "name": "glance",
                                                "file_system": "xfs",
                                                "size": 14540
                                            }
                                        ],
                                        "type": "vg",
                                        "id": "image"
                                    },
                                    {
                                        "_allocate_size": "min",
                                        "label": "Mysql Database",
                                        "min_size": 20480,
                                        "volumes": [
                                            {
                                                "mount": "/var/lib/mysql",
                                                "type": "lv",
                                                "name": "root",
                                                "file_system": "ext4",
                                                "size": 20480
                                            }
                                        ],
                                        "type": "vg",
                                        "id": "mysql"
                                    },
                                    {
                                        "_allocate_size": "min",
                                        "label": "Horizon Temp Storage",
                                        "min_size": 11264,
                                        "volumes": [
                                            {
                                                "mount": "/var/lib/horizon",
                                                "type": "lv",
                                                "name": "horizontmp",
                                                "file_system": "xfs",
                                                "size": 11264
                                            }
                                        ],
                                        "type": "vg",
                                        "id": "horizon"
                                    }
                                ]
                            },
                            "master_ip": "10.20.0.2",
                            "cloud_init_templates": {
                                "cloud_config": "cloud_config_fuel_9.0_ubuntu.jinja2",
                                "meta_data": "meta_data_fuel_9.0_ubuntu.jinja2",
                                "boothook": "boothook_fuel_9.0_ubuntu.jinja2"
                            },
                            "admin_net": "10.20.0.0/24",
                            "mco_host": "10.20.0.2",
                            "authorized_keys": [
                                "\"ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQD5dzcY/wMTG7TFwNV2fakO9B6fRy9BpTW9Va4TRN+3KHQgV/5ZYqdFRcqjQU5EqFQR50ThOrTVWjO6lbqINhSqOVKJ0wpUkdB5Fd+ovevSs+VywQbVW6RBU+YE34mlUgsZ+UJ5K4vAWV2IIp0FHikJ3ehr2FQMvJb9B+l3SpNw7hjKCOQ9KHBzofMnaq9QqZyvjRchd7zmIrJO+DV+MQDxZ4AqmQBzCVXjQK3RJ2a9ulBVw7ypQ1qyHm2JDtWxrCoEXDEGYAKrVMxHPWXKOpHtVe0+1trIN6uWtLyDRmHvma4ApiiLCJFQo42KigWz//MB+duHLosGgtEwBIFDWOZp root@xcloudos.domain.tld\""
                            ],
                            "mco_vhost": "mcollective",
                            "repo_setup": {
                                "installer_kernel": {
                                    "local": "/var/www/nailgun/ubuntu/x86_64/images/linux",
                                    "remote_relative": "dists/trusty/main/installer-amd64/current/images/netboot/ubuntu-installer/amd64/linux"
                                },
                                "repos": [
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
                                "metadata": {
                                    "group": "general",
                                    "always_editable": true,
                                    "weight": 50,
                                    "label": "Repositories"
                                },
                                "installer_initrd": {
                                    "local": "/var/www/nailgun/ubuntu/x86_64/images/initrd.gz",
                                    "remote_relative": "dists/trusty/main/installer-amd64/current/images/netboot/ubuntu-installer/amd64/initrd.gz"
                                }
                            },
                            "mco_pskey": "unset",
                            "puppet_enable": 0,
                            "fuel_version": "9.0",
                            "puppet_auto_setup": 1,
                            "mco_auto_setup": 1,
                            "mco_password": "VVf88IhkApAJFpRxFSzvOc2X",
                            "auth_key": "\"\"",
                            "mco_connector": "rabbitmq"
                        },
                        "name": "node-4",
                        "hostname": "node-4.domain.tld",
                        "slave_name": "node-4",
                        "power_pass": "/root/.ssh/bootstrap.rsa",
                        "netboot_enabled": "1"
                    }
                ],
                # fault_tolerance
                "fault_tolerance": [
                    {
                        "percentage": 2,
                        "uids": []
                    }
                ],
                # serialize_pre_provision_tasks: nailgun/orchestrator/tasks_templates.py: make_provisioning_images_task
                "pre_provision": [
                    {
                        "priority": 100,
                        "type": "shell",
                        "id": null,
                        "parameters": {
                            "retries": 1,
                            "cmd": "fa_build_image --image_build_dir /var/lib/fuel/ibp --log-file /var/log/fuel-agent-env-1.log --data_driver nailgun_build_image --input_data '{\"image_data\": {\"/boot\": {\"container\": \"gzip\", \"uri\": \"http://10.20.0.2:8080/targetimages/env_1_ubuntu_1404_amd64-boot.img.gz\", \"format\": \"ext2\"}, \"/\": {\"container\": \"gzip\", \"uri\": \"http://10.20.0.2:8080/targetimages/env_1_ubuntu_1404_amd64.img.gz\", \"format\": \"ext4\"}}, \"output\": \"/var/www/nailgun/targetimages\", \"repos\": [{\"name\": \"ubuntu\", \"section\": \"main universe multiverse\", \"uri\": \"http://archive.ubuntu.com/ubuntu/\", \"priority\": null, \"suite\": \"trusty\", \"type\": \"deb\"}, {\"name\": \"ubuntu-updates\", \"section\": \"main universe multiverse\", \"uri\": \"http://archive.ubuntu.com/ubuntu/\", \"priority\": null, \"suite\": \"trusty-updates\", \"type\": \"deb\"}, {\"name\": \"ubuntu-security\", \"section\": \"main universe multiverse\", \"uri\": \"http://archive.ubuntu.com/ubuntu/\", \"priority\": null, \"suite\": \"trusty-security\", \"type\": \"deb\"}, {\"name\": \"mos\", \"section\": \"main restricted\", \"uri\": \"http://10.20.0.2:8080/mitaka-9.0/ubuntu/x86_64\", \"priority\": 1050, \"suite\": \"mos9.0\", \"type\": \"deb\"}, {\"name\": \"mos-updates\", \"section\": \"main restricted\", \"uri\": \"http://mirror.fuel-infra.org/mos-repos/ubuntu/9.0/\", \"priority\": 1050, \"suite\": \"mos9.0-updates\", \"type\": \"deb\"}, {\"name\": \"mos-security\", \"section\": \"main restricted\", \"uri\": \"http://mirror.fuel-infra.org/mos-repos/ubuntu/9.0/\", \"priority\": 1050, \"suite\": \"mos9.0-security\", \"type\": \"deb\"}, {\"name\": \"mos-holdback\", \"section\": \"main restricted\", \"uri\": \"http://mirror.fuel-infra.org/mos-repos/ubuntu/9.0/\", \"priority\": 1100, \"suite\": \"mos9.0-holdback\", \"type\": \"deb\"}, {\"name\": \"Auxiliary\", \"section\": \"main restricted\", \"uri\": \"http://10.20.0.2:8080/mitaka-9.0/ubuntu/auxiliary\", \"priority\": 1150, \"suite\": \"auxiliary\", \"type\": \"deb\"}], \"packages\": [\"acl\", \"anacron\", \"bash-completion\", \"bridge-utils\", \"bsdmainutils\", \"build-essential\", \"cloud-init\", \"curl\", \"daemonize\", \"debconf-utils\", \"gdisk\", \"grub-pc\", \"hpsa-dkms\", \"hwloc\", \"i40e-dkms\", \"linux-firmware\", \"linux-firmware-nonfree\", \"linux-headers-generic-lts-trusty\", \"linux-image-generic-lts-trusty\", \"lvm2\", \"mcollective\", \"mdadm\", \"multipath-tools\", \"multipath-tools-boot\", \"nailgun-agent\", \"nailgun-mcagents\", \"network-checker\", \"ntp\", \"openssh-client\", \"openssh-server\", \"puppet\", \"python-amqp\", \"ruby-augeas\", \"ruby-ipaddress\", \"ruby-json\", \"ruby-netaddr\", \"ruby-openstack\", \"ruby-shadow\", \"ruby-stomp\", \"systemd-shim\", \"telnet\", \"ubuntu-minimal\", \"ubuntu-standard\", \"uuid-runtime\", \"vim\", \"virt-what\", \"vlan\", \"xcloud-init\"], \"codename\": \"trusty\"}'",
                            "cwd": "/",
                            "timeout": 3600,
                            "interval": 1
                        },
                        "uids": [
                            "master"
                        ]
                    }
                ]
            }
        },
        "respond_to": "provision_resp",
        "method": "image_provision",
        "api_version": "1"
    },
    {
        "args": {
            "tasks_directory": {},
            "dry_run": false,
            "tasks_metadata": {
                "fault_tolerance_groups": [
                    {
                        "fault_tolerance": 0,
                        "name": "primary-controller",
                        "node_ids": [
                            "4"
                        ]
                    }
                ]
            },
            "task_uuid": "30581515-0e6f-4c9d-9b10-b67fa179fc29",
            "debug": true,
            "tasks_graph": {
                "4": [
                    {
                        "type": "skipped",
                        "fail_on_error": false,
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "enable_quorum"
                            },
                            {
                                "node_id": "4",
                                "name": "enable_rados"
                            }
                        ],
                        "id": "ironic_post_swift_key",
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "post_deployment_end"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/openstack-haproxy/openstack-haproxy-mysqld.pp",
                            "timeout": 300,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-cluster-haproxy"
                            },
                            {
                                "node_id": null,
                                "name": "deploy_start"
                            }
                        ],
                        "id": "openstack-haproxy-mysqld",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/openstack-network/server-config.pp",
                            "timeout": 1800,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "openstack-network-common-config"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-network-start"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-rabbitmq"
                            }
                        ],
                        "id": "primary-openstack-network-server-config",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "openstack-network-end"
                            }
                        ],
                        "type": "puppet"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/openstack-cinder/db.pp",
                            "timeout": 1800,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-database"
                            }
                        ],
                        "id": "cinder-db",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "openstack-cinder"
                            }
                        ],
                        "type": "puppet"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/netconfig/netconfig.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "tools"
                            }
                        ],
                        "id": "netconfig",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/astute/dump_rabbitmq_definitions.pp",
                            "timeout": 180,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": null,
                                "name": "post_deployment_start"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "post_deployment_end"
                            }
                        ],
                        "type": "puppet",
                        "id": "dump_rabbitmq_definitions"
                    },
                    {
                        "fail_on_error": true,
                        "type": "sync",
                        "id": "rsync_core_puppet",
                        "parameters": {
                            "src": "rsync://10.20.0.2:/puppet/mitaka-9.0/modules/",
                            "dst": "/etc/puppet/modules",
                            "cwd": "/",
                            "timeout": 180
                        },
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "pre_deployment_start"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/keystone/openrc_generate.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-keystone"
                            },
                            {
                                "node_id": "4",
                                "name": "openrc-delete"
                            }
                        ],
                        "id": "keystone-openrc-generate",
                        "fail_on_error": true,
                        "type": "puppet"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/openstack-cinder/create_cinder_types.pp",
                            "timeout": 1200,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "openstack-cinder"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet",
                        "id": "create-cinder-types"
                    },
                    {
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "ceilometer-keystone"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-haproxy"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-rabbitmq"
                            }
                        ],
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "primary-openstack-controller"
                            }
                        ],
                        "type": "skipped",
                        "id": "ceilometer-controller"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/hiera/override_configuration.pp",
                            "timeout": 180,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "pre_hiera_config"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "pre_deployment_start"
                            }
                        ],
                        "type": "puppet",
                        "id": "override_configuration"
                    },
                    {
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-keystone"
                            }
                        ],
                        "id": "ceilometer-keystone",
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "ceilometer-controller"
                            }
                        ],
                        "type": "skipped"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/openstack-controller/db.pp",
                            "timeout": 1800,
                            "cwd": "/"
                        },
                        "type": "puppet",
                        "id": "nova-db",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "primary-openstack-controller"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-database"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/keystone/workloads_collector_add.pp",
                            "timeout": 1800,
                            "cwd": "/"
                        },
                        "type": "puppet",
                        "id": "workloads_collector_add",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-keystone"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/openstack-network/plugins/ml2.pp",
                            "timeout": 1800,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "openstack-network-common-config"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-openstack-network-server-config"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-network-start"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-rabbitmq"
                            }
                        ],
                        "id": "primary-openstack-network-plugins-l2",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "openstack-network-end"
                            }
                        ],
                        "type": "puppet"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/hiera/hiera.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "rsync_core_puppet"
                            },
                            {
                                "node_id": null,
                                "name": "deploy_start"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "setup_repositories"
                            }
                        ],
                        "type": "puppet",
                        "id": "hiera"
                    },
                    {
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "keystone-openrc-generate"
                            },
                            {
                                "node_id": "4",
                                "name": "keystone-db"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-keystone"
                            }
                        ],
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "primary-ceph-radosgw"
                            }
                        ],
                        "type": "skipped",
                        "id": "radosgw-keystone"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/virtual_ips/virtual_ips.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-cluster"
                            },
                            {
                                "node_id": "4",
                                "name": "cluster"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet",
                        "id": "virtual_ips"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/dns/dns-server.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "openstack-haproxy"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet",
                        "id": "primary-dns-server"
                    },
                    {
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-cluster-haproxy"
                            },
                            {
                                "node_id": null,
                                "name": "deploy_start"
                            }
                        ],
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "skipped",
                        "id": "openstack-haproxy-murano"
                    },
                    {
                        "fail_on_error": false,
                        "type": "skipped",
                        "id": "openstack-network-end",
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/openstack-haproxy/openstack-haproxy-radosgw.pp",
                            "timeout": 300,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-cluster-haproxy"
                            },
                            {
                                "node_id": null,
                                "name": "deploy_start"
                            }
                        ],
                        "id": "openstack-haproxy-radosgw",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/openstack-haproxy/openstack-haproxy-swift.pp",
                            "timeout": 300,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-cluster-haproxy"
                            },
                            {
                                "node_id": null,
                                "name": "deploy_start"
                            }
                        ],
                        "id": "openstack-haproxy-swift",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/heat/db.pp",
                            "timeout": 1800,
                            "cwd": "/"
                        },
                        "type": "puppet",
                        "id": "heat-db",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "primary-heat"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-database"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/openstack-haproxy/openstack-haproxy-neutron.pp",
                            "timeout": 300,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-cluster-haproxy"
                            },
                            {
                                "node_id": null,
                                "name": "deploy_start"
                            }
                        ],
                        "id": "openstack-haproxy-neutron",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet"
                    },
                    {
                        "type": "skipped",
                        "fail_on_error": false,
                        "requires": [
                            {
                                "node_id": null,
                                "name": "post_deployment_start"
                            }
                        ],
                        "id": "updatedb",
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "post_deployment_end"
                            }
                        ]
                    },
                    {
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-database"
                            }
                        ],
                        "id": "ironic-db",
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "ironic-api"
                            }
                        ],
                        "type": "skipped"
                    },
                    {
                        "type": "skipped",
                        "fail_on_error": false,
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "configuration_symlink"
                            }
                        ],
                        "id": "plugins_rsync",
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "pre_deployment_start"
                            }
                        ]
                    },
                    {
                        "type": "skipped",
                        "fail_on_error": false,
                        "requires": [
                            {
                                "node_id": null,
                                "name": "post_deployment_start"
                            },
                            {
                                "node_id": "4",
                                "name": "enable_rados"
                            }
                        ],
                        "id": "ceilometer-radosgw-user",
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "post_deployment_end"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/openstack-haproxy/openstack-haproxy-keystone.pp",
                            "timeout": 300,
                            "cwd": "/"
                        },
                        "type": "puppet",
                        "id": "openstack-haproxy-keystone",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-cluster-haproxy"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/hosts/hosts.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "netconfig"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet",
                        "id": "hosts"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "strategy": {
                                "amount": 3,
                                "type": "parallel"
                            },
                            "cwd": "/",
                            "timeout": 3600,
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/rabbitmq/rabbitmq.pp"
                        },
                        "type": "puppet",
                        "id": "primary-rabbitmq",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            },
                            {
                                "node_id": "4",
                                "name": "glance"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-openstack-controller"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-cluster"
                            },
                            {
                                "node_id": "4",
                                "name": "cluster"
                            },
                            {
                                "node_id": "4",
                                "name": "netconfig"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "strategy": {
                                "amount": 6,
                                "type": "parallel"
                            },
                            "cwd": "/",
                            "timeout": 3600,
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/cluster-haproxy/cluster-haproxy.pp"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-cluster"
                            },
                            {
                                "node_id": "4",
                                "name": "virtual_ips"
                            },
                            {
                                "node_id": null,
                                "name": "deploy_start"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet",
                        "id": "primary-cluster-haproxy"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/openstack-network/routers.pp",
                            "timeout": 1800,
                            "cwd": "/"
                        },
                        "type": "puppet",
                        "id": "openstack-network-routers",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "openstack-network-end"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "openstack-network-start"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-network-networks"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/netconfig/reserved_ports.pp",
                            "timeout": 180,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "rsync_core_puppet"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "globals"
                            }
                        ],
                        "type": "puppet",
                        "id": "reserved_ports"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/roles/controller.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-openstack-controller"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet",
                        "id": "controller_remaining_tasks"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/glance/keystone.pp",
                            "timeout": 1800,
                            "cwd": "/"
                        },
                        "type": "puppet",
                        "id": "glance-keystone",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "glance"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-keystone"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/openstack-haproxy/openstack-haproxy-aodh.pp",
                            "timeout": 300,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-cluster-haproxy"
                            },
                            {
                                "node_id": null,
                                "name": "deploy_start"
                            }
                        ],
                        "id": "openstack-haproxy-aodh",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet"
                    },
                    {
                        "type": "skipped",
                        "fail_on_error": false,
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "murano"
                            }
                        ],
                        "id": "murano-cfapi"
                    },
                    {
                        "type": "skipped",
                        "fail_on_error": false,
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "controller_remaining_tasks"
                            }
                        ],
                        "id": "vmware-vcenter",
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ]
                    },
                    {
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "openstack-network-end"
                            },
                            {
                                "node_id": "4",
                                "name": "memcached"
                            },
                            {
                                "node_id": "4",
                                "name": "ironic-api"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-rabbitmq"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-openstack-controller"
                            }
                        ],
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "skipped",
                        "id": "ironic-compute"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/openstack-network/agents/metadata.pp",
                            "timeout": 1800,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "openstack-network-common-config"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-rabbitmq"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-openstack-network-server-config"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-network-start"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-openstack-network-agents-l3"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-openstack-network-plugins-l2"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-network-server-nova"
                            }
                        ],
                        "id": "primary-openstack-network-agents-metadata",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "openstack-network-end"
                            }
                        ],
                        "type": "puppet"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules/",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/openstack-cinder/keystone.pp",
                            "timeout": 1800,
                            "cwd": "/"
                        },
                        "type": "puppet",
                        "id": "cinder-keystone",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "openstack-cinder"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-keystone"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "files": [
                                {
                                    "src": "/var/lib/fuel/keys/1/neutron/neutron.pub",
                                    "dst": "/var/lib/astute/neutron/neutron.pub"
                                },
                                {
                                    "src": "/var/lib/fuel/keys/1/neutron/neutron",
                                    "dst": "/var/lib/astute/neutron/neutron"
                                },
                                {
                                    "src": "/var/lib/fuel/keys/1/nova/nova.pub",
                                    "dst": "/var/lib/astute/nova/nova.pub"
                                },
                                {
                                    "src": "/var/lib/fuel/keys/1/nova/nova",
                                    "dst": "/var/lib/astute/nova/nova"
                                },
                                {
                                    "src": "/var/lib/fuel/keys/1/mysql/mysql.pub",
                                    "dst": "/var/lib/astute/mysql/mysql.pub"
                                },
                                {
                                    "src": "/var/lib/fuel/keys/1/mysql/mysql",
                                    "dst": "/var/lib/astute/mysql/mysql"
                                },
                                {
                                    "src": "/var/lib/fuel/keys/1/mongodb/mongodb.key",
                                    "dst": "/var/lib/astute/mongodb/mongodb.key"
                                },
                                {
                                    "src": "/var/lib/fuel/keys/1/fernet-keys/0",
                                    "dst": "/var/lib/astute/keystone/0"
                                },
                                {
                                    "src": "/var/lib/fuel/keys/1/fernet-keys/1",
                                    "dst": "/var/lib/astute/keystone/1"
                                }
                            ],
                            "dir_permissions": "0700",
                            "cwd": "/",
                            "permissions": "0600"
                        },
                        "requires": [
                            {
                                "node_id": "master",
                                "name": "generate_keys"
                            }
                        ],
                        "id": "copy_keys",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "pre_deployment_end"
                            }
                        ],
                        "type": "copy_files"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/tools/tools.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "logging"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet",
                        "id": "tools"
                    },
                    {
                        "requires": [
                            {
                                "node_id": null,
                                "name": "post_deployment_start"
                            }
                        ],
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "upload_cirros"
                            },
                            {
                                "node_id": null,
                                "name": "post_deployment_end"
                            }
                        ],
                        "type": "skipped",
                        "id": "enable_rados"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/keystone/purge_old_admin.pp",
                            "timeout": 180,
                            "cwd": "/"
                        },
                        "type": "puppet",
                        "id": "delete_old_admin_user",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "post_deployment_end"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-keystone"
                            },
                            {
                                "node_id": null,
                                "name": "post_deployment_start"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/ntp/ntp-check.pp",
                            "timeout": 600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "dns-client"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "ntp-server"
                            }
                        ],
                        "type": "puppet",
                        "id": "ntp-check"
                    },
                    {
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-database"
                            }
                        ],
                        "id": "aodh-db",
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "aodh"
                            }
                        ],
                        "type": "skipped"
                    },
                    {
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "upload_cirros"
                            }
                        ],
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "post_deployment_end"
                            }
                        ],
                        "type": "skipped",
                        "id": "disable_keystone_service_token"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/umm/umm.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "tools"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet",
                        "id": "umm"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/memcached/memcached.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "type": "puppet",
                        "id": "memcached",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-keystone"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "netconfig"
                            }
                        ]
                    },
                    {
                        "type": "skipped",
                        "fail_on_error": false,
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "setup_repositories"
                            }
                        ],
                        "id": "allocate_hugepages",
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "globals"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/keystone/openrc_delete.pp",
                            "timeout": 90,
                            "cwd": "/"
                        },
                        "type": "puppet",
                        "id": "openrc-delete",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "primary-keystone"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "openstack-haproxy"
                            },
                            {
                                "node_id": null,
                                "name": "deploy_start"
                            }
                        ]
                    },
                    {
                        "type": "skipped",
                        "fail_on_error": false,
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "plugins_rsync"
                            }
                        ],
                        "id": "plugins_setup_repositories",
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "pre_deployment_start"
                            }
                        ]
                    },
                    {
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-keystone"
                            }
                        ],
                        "id": "sahara-keystone",
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "sahara"
                            }
                        ],
                        "type": "skipped"
                    },
                    {
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-cluster-haproxy"
                            },
                            {
                                "node_id": null,
                                "name": "deploy_start"
                            }
                        ],
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "skipped",
                        "id": "openstack-haproxy-sahara"
                    },
                    {
                        "type": "skipped",
                        "fail_on_error": false,
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "firewall"
                            }
                        ],
                        "id": "ssl-keys-saving",
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/cluster/cluster.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "hosts"
                            },
                            {
                                "node_id": "4",
                                "name": "firewall"
                            },
                            {
                                "node_id": null,
                                "name": "deploy_start"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet",
                        "id": "primary-cluster"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/astute/upload_cirros.pp",
                            "timeout": 300,
                            "cwd": "/"
                        },
                        "type": "puppet",
                        "id": "upload_cirros",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "post_deployment_end"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-keystone"
                            },
                            {
                                "node_id": "4",
                                "name": "enable_quorum"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/keystone/keystone.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "type": "puppet",
                        "id": "primary-keystone",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "primary-openstack-controller"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-database"
                            },
                            {
                                "node_id": "4",
                                "name": "keystone-db"
                            },
                            {
                                "node_id": "4",
                                "name": "memcached"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-haproxy"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-rabbitmq"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/openstack-network/agents/l3.pp",
                            "timeout": 1800,
                            "cwd": "/"
                        },
                        "type": "puppet",
                        "id": "primary-openstack-network-agents-l3",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "openstack-network-end"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "openstack-network-routers"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-rabbitmq"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-network-start"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-openstack-network-plugins-l2"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-network-networks"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "dir_permissions": "0750",
                            "timeout": 180,
                            "path": "/etc/fuel/cluster/1/astute.yaml",
                            "data": "access:\n  email: admin@localhost\n  metadata:\n    group: general\n    label: OpenStack Access\n    weight: 10\n  password: admin\n  tenant: admin\n  user: admin\naodh:\n  db_password: QAKwUwho9BHYfTMyfOG2WnyZ\n  user_password: xz8gSdAkeIe7djhGN1BOr0gn\nauth_key: ''\nauto_assign_floating_ip: false\nbase_syslog:\n  syslog_port: '514'\n  syslog_server: 10.20.0.2\nceilometer:\n  db_password: 8tEYmdeKgsN3Atwk5idQonY0\n  enabled: false\n  metering_secret: QargkI39hic5U5lWZ0zPlSSU\n  user_password: DxBTOrMG0RT6gfgkAiWAWXdn\ncgroups:\n  metadata:\n    always_editable: true\n    group: general\n    label: Cgroups conguration for services\n    restrictions:\n    - action: hide\n      condition: 'true'\n    weight: 90\ncinder:\n  db_password: C2QsaX7mybOsScjnP84yB0o6\n  fixed_key: dc98130bd65d926c6c6d76408e1607bc871b6f23f4cbbe70bde0ee2da1bba647\n  user_password: 3rVZf2gQNwN14aP9jATCAQlA\ncluster:\n  fuel_version: '9.0'\n  id: 1\n  mode: ha_compact\n  name: test-env-kvm-default\n  status: deployment\ncobbler:\n  profile: ubuntu_1404_x86_64\nconfiguration:\n  nova_config:\n    DEFAULT/debug:\n      value: true\nconfiguration_options: {}\ncorosync:\n  group: 226.94.1.1\n  metadata:\n    group: general\n    label: Corosync\n    restrictions:\n    - action: hide\n      condition: 'true'\n    weight: 50\n  port: '12000'\n  verified: false\ndebug: false\ndeployed_before:\n  value: false\ndeployment_id: 1\ndeployment_mode: ha_compact\nexternal_dns:\n  dns_list: null\n  metadata:\n    group: network\n    label: Host OS DNS Servers\n    weight: 30\nexternal_mongo:\n  hosts_ip: ''\n  metadata:\n    group: openstack_services\n    label: External MongoDB\n    restrictions:\n    - action: hide\n      condition: settings:additional_components.mongo.value == false\n      message: Ceilometer and MongoDB are not enabled on the Additional Components\n        section\n    weight: 30\n  mongo_db_name: ceilometer\n  mongo_password: ceilometer\n  mongo_replset: ''\n  mongo_user: ceilometer\nexternal_ntp:\n  metadata:\n    group: network\n    label: Host OS NTP Servers\n    weight: 40\n  ntp_list:\n  - 0.fuel.pool.ntp.org\n  - 1.fuel.pool.ntp.org\n  - 2.fuel.pool.ntp.org\nfail_if_error: true\nfqdn: node-4.domain.tld\nfuel_version: '9.0'\nglance:\n  db_password: XVyVtsbNI6iAtfzFblvu91Tz\n  image_cache_max_size: '5368709120'\n  user_password: ym4tpW1WUqvgYTvXWJT4kNYb\nglance_glare:\n  user_password: Qxv2ITExQZshZtgTf5sGH0jD\nheat:\n  auth_encryption_key: 754ce969bb3a3f5c7d208cce18655cdc\n  db_password: 4WzfoHZdjW7YLtUvYY1z6fsU\n  enabled: true\n  rabbit_password: LVzQQM48AxY65m86l0fG1wwk\n  user_password: v05jnvd9pQHVt1pufEhLWkFs\nhorizon:\n  secret_key: e8555623051accac68498e324b81c2ec15d21698f24d7796e20f6bc8815f9422\nironic:\n  db_password: RL6LqSDeb3eCWlJ2iTfL0l6o\n  enabled: false\n  swift_tempurl_key: yQ8wLkGKwmZ3TVZZul0IL6ca\n  user_password: XnNHZfQoK3ECDTkCeaRo56i3\nkernel_params:\n  kernel: console=tty0 net.ifnames=1 biosdevname=0 rootdelay=90 nomodeset\n  metadata:\n    group: general\n    label: Kernel parameters\n    weight: 60\nkeystone:\n  admin_token: wbbKYog35s0tBi0f9aiFlbvQ\n  db_password: jOkp5667FUNSH4XCbtUSOl7a\nlast_controller: node-4\nlibvirt_type: kvm\nmanagement_network_range: 192.168.0.0/24\nmaster_ip: 10.20.0.2\nmetadata:\n  label: Common\n  weight: 10\nmongo:\n  enabled: false\nmp:\n- point: '1'\n  weight: '1'\n- point: '2'\n  weight: '2'\nmurano:\n  db_password: P6tvepoN0mfniuQhxl7KQiHy\n  enabled: false\n  rabbit_password: Zk1IKuOinV83zz9YlLiJ0Yx5\n  user_password: Y8EL8pIzCvmpBq64bHn6lMoQ\nmurano-cfapi:\n  db_password: wv0gi7oOmcaf2Ckma4HLJX5L\n  enabled: false\n  rabbit_password: xK1uayOY6eWq9huAwJ3WEXeF\n  user_password: MKakPrUHJkQdmYuycpNIqRBS\nmurano_settings:\n  metadata:\n    group: openstack_services\n    label: Murano Settings\n    restrictions:\n    - action: hide\n      condition: settings:additional_components.murano.value == false\n      message: Murano is not enabled on the Additional Components section\n    weight: 20\n  murano_glance_artifacts_plugin: true\n  murano_repo_url: http://storage.apps.openstack.org/\nmysql:\n  root_password: dG9TwqNWB3y4iLUWWZGxBbKI\n  wsrep_password: cXpzUQ0IYjuDA44MFnlA4TM4\nnetwork_metadata:\n  nodes:\n    node-4:\n      fqdn: node-4.domain.tld\n      name: node-4\n      network_roles:\n        admin/pxe: 10.20.0.3\n        aodh/api: 192.168.0.3\n        ceilometer/api: 192.168.0.3\n        ceph/public: 192.168.1.1\n        ceph/radosgw: 192.168.36.152\n        ceph/replication: 192.168.1.1\n        cinder/api: 192.168.0.3\n        cinder/iscsi: 192.168.1.1\n        ex: 192.168.36.152\n        fw-admin: 10.20.0.3\n        glance/api: 192.168.0.3\n        glance/glare: 192.168.0.3\n        heat/api: 192.168.0.3\n        horizon: 192.168.0.3\n        ironic/api: 192.168.0.3\n        keystone/api: 192.168.0.3\n        management: 192.168.0.3\n        mgmt/corosync: 192.168.0.3\n        mgmt/database: 192.168.0.3\n        mgmt/memcache: 192.168.0.3\n        mgmt/messaging: 192.168.0.3\n        mgmt/vip: 192.168.0.3\n        mongo/db: 192.168.0.3\n        murano/api: 192.168.0.3\n        murano/cfapi: 192.168.0.3\n        neutron/api: 192.168.0.3\n        neutron/floating: null\n        neutron/private: null\n        nova/api: 192.168.0.3\n        nova/migration: 192.168.0.3\n        public/vip: 192.168.36.152\n        sahara/api: 192.168.0.3\n        storage: 192.168.1.1\n        swift/api: 192.168.0.3\n        swift/replication: 192.168.1.1\n      node_roles:\n      - primary-controller\n      - primary-database\n      - primary-keystone\n      - primary-neutron\n      - primary-rabbitmq\n      nova_cpu_pinning_enabled: false\n      nova_hugepages_enabled: false\n      swift_zone: '4'\n      uid: '4'\n      user_node_name: Untitled (ea:68)\n  vips:\n    management:\n      ipaddr: 192.168.0.2\n      is_user_defined: false\n      namespace: haproxy\n      network_role: mgmt/vip\n      node_roles:\n      - controller\n      - primary-controller\n      vendor_specific: null\n    public:\n      ipaddr: 192.168.36.151\n      is_user_defined: false\n      namespace: haproxy\n      network_role: public/vip\n      node_roles:\n      - controller\n      - primary-controller\n      vendor_specific: null\n    vrouter:\n      ipaddr: 192.168.0.1\n      is_user_defined: false\n      namespace: vrouter\n      network_role: mgmt/vip\n      node_roles:\n      - controller\n      - primary-controller\n      vendor_specific: null\n    vrouter_pub:\n      ipaddr: 192.168.36.150\n      is_user_defined: false\n      namespace: vrouter\n      network_role: public/vip\n      node_roles:\n      - controller\n      - primary-controller\n      vendor_specific:\n        iptables_rules:\n          ns_start:\n          - iptables -t nat -A POSTROUTING -o <%INT%> -j MASQUERADE\n          ns_stop:\n          - iptables -t nat -D POSTROUTING -o <%INT%> -j MASQUERADE\nnetwork_scheme:\n  endpoints:\n    br-ex:\n      IP:\n      - 192.168.36.152/24\n      gateway: 192.168.36.254\n      vendor_specific:\n        provider_gateway: 192.168.36.254\n    br-floating:\n      IP: none\n    br-fw-admin:\n      IP:\n      - 10.20.0.3/24\n      vendor_specific:\n        provider_gateway: 10.20.0.2\n    br-mgmt:\n      IP:\n      - 192.168.0.3/24\n    br-prv:\n      IP: none\n    br-storage:\n      IP:\n      - 192.168.1.1/24\n  interfaces:\n    eth0:\n      ethtool:\n        offload: {}\n      vendor_specific:\n        bus_info: '0000:00:03.0'\n        driver: virtio_net\n    eth1:\n      ethtool:\n        offload: {}\n      vendor_specific:\n        bus_info: '0000:00:04.0'\n        driver: virtio_net\n    eth2:\n      ethtool:\n        offload: {}\n      vendor_specific:\n        bus_info: '0000:00:05.0'\n        driver: virtio_net\n    eth3:\n      ethtool:\n        offload: {}\n      vendor_specific:\n        bus_info: '0000:00:06.0'\n        driver: virtio_net\n  provider: lnx\n  roles:\n    admin/pxe: br-fw-admin\n    aodh/api: br-mgmt\n    ceilometer/api: br-mgmt\n    ceph/public: br-storage\n    ceph/radosgw: br-ex\n    ceph/replication: br-storage\n    cinder/api: br-mgmt\n    cinder/iscsi: br-storage\n    ex: br-ex\n    fw-admin: br-fw-admin\n    glance/api: br-mgmt\n    glance/glare: br-mgmt\n    heat/api: br-mgmt\n    horizon: br-mgmt\n    ironic/api: br-mgmt\n    keystone/api: br-mgmt\n    management: br-mgmt\n    mgmt/corosync: br-mgmt\n    mgmt/database: br-mgmt\n    mgmt/memcache: br-mgmt\n    mgmt/messaging: br-mgmt\n    mgmt/vip: br-mgmt\n    mongo/db: br-mgmt\n    murano/api: br-mgmt\n    murano/cfapi: br-mgmt\n    neutron/api: br-mgmt\n    neutron/floating: br-floating\n    neutron/private: br-prv\n    nova/api: br-mgmt\n    nova/migration: br-mgmt\n    public/vip: br-ex\n    sahara/api: br-mgmt\n    storage: br-storage\n    swift/api: br-mgmt\n    swift/replication: br-storage\n  transformations:\n  - action: add-br\n    name: br-fw-admin\n  - action: add-br\n    name: br-mgmt\n  - action: add-br\n    name: br-storage\n  - action: add-br\n    name: br-ex\n  - action: add-br\n    name: br-floating\n    provider: ovs\n  - action: add-patch\n    bridges:\n    - br-floating\n    - br-ex\n    mtu: 65000\n    provider: ovs\n  - action: add-br\n    name: br-prv\n    provider: ovs\n  - action: add-br\n    name: br-aux\n  - action: add-patch\n    bridges:\n    - br-prv\n    - br-aux\n    mtu: 65000\n    provider: ovs\n  - action: add-port\n    bridge: br-fw-admin\n    name: eth0\n  - action: add-port\n    bridge: br-ex\n    name: eth1\n  - action: add-port\n    bridge: br-aux\n    name: eth2\n  - action: add-port\n    bridge: br-mgmt\n    name: eth2.101\n  - action: add-port\n    bridge: br-storage\n    name: eth3.102\n  version: '1.1'\nneutron_advanced_configuration:\n  metadata:\n    group: network\n    label: Neutron Advanced Configuration\n    restrictions:\n    - action: hide\n      condition: cluster:net_provider != 'neutron'\n    weight: 20\n  neutron_dvr: false\n  neutron_l2_pop: false\n  neutron_l3_ha: false\n  neutron_qos: false\nnode_volumes:\n- bootable: true\n  extra: []\n  free_space: 81100\n  id: vda\n  name: vda\n  size: 81920\n  type: disk\n  volumes:\n  - size: 300\n    type: boot\n  - file_system: ext2\n    mount: /boot\n    name: Boot\n    size: 200\n    type: partition\n  - size: 0\n    type: lvm_meta_pool\n  - lvm_meta_size: 64\n    size: 24640\n    type: pv\n    vg: os\n  - lvm_meta_size: 64\n    size: 10304\n    type: pv\n    vg: logs\n  - lvm_meta_size: 64\n    size: 20544\n    type: pv\n    vg: mysql\n  - lvm_meta_size: 64\n    size: 11328\n    type: pv\n    vg: horizon\n  - lvm_meta_size: 64\n    size: 14604\n    type: pv\n    vg: image\n- _allocate_size: min\n  id: os\n  label: Base System\n  min_size: 24576\n  type: vg\n  volumes:\n  - file_system: ext4\n    mount: /\n    name: root\n    size: 16384\n    type: lv\n  - file_system: swap\n    mount: swap\n    name: swap\n    size: 8192\n    type: lv\n- _allocate_size: min\n  id: logs\n  label: Logs\n  min_size: 10240\n  type: vg\n  volumes:\n  - file_system: ext4\n    mount: /var/log\n    name: log\n    size: 10240\n    type: lv\n- _allocate_size: all\n  id: image\n  label: Image Storage\n  min_size: 5120\n  type: vg\n  volumes:\n  - file_system: xfs\n    mount: /var/lib/glance\n    name: glance\n    size: 14540\n    type: lv\n- _allocate_size: min\n  id: mysql\n  label: Mysql Database\n  min_size: 20480\n  type: vg\n  volumes:\n  - file_system: ext4\n    mount: /var/lib/mysql\n    name: root\n    size: 20480\n    type: lv\n- _allocate_size: min\n  id: horizon\n  label: Horizon Temp Storage\n  min_size: 11264\n  type: vg\n  volumes:\n  - file_system: xfs\n    mount: /var/lib/horizon\n    name: horizontmp\n    size: 11264\n    type: lv\nnodes:\n- fqdn: node-4.domain.tld\n  internal_address: 192.168.0.3\n  internal_netmask: 255.255.255.0\n  name: node-4\n  public_address: 192.168.36.152\n  public_netmask: 255.255.255.0\n  role: primary-controller\n  storage_address: 192.168.1.1\n  storage_netmask: 255.255.255.0\n  swift_zone: '4'\n  uid: '4'\n  user_node_name: Untitled (ea:68)\n- fqdn: node-4.domain.tld\n  internal_address: 192.168.0.3\n  internal_netmask: 255.255.255.0\n  name: node-4\n  public_address: 192.168.36.152\n  public_netmask: 255.255.255.0\n  role: primary-database\n  storage_address: 192.168.1.1\n  storage_netmask: 255.255.255.0\n  swift_zone: '4'\n  uid: '4'\n  user_node_name: Untitled (ea:68)\n- fqdn: node-4.domain.tld\n  internal_address: 192.168.0.3\n  internal_netmask: 255.255.255.0\n  name: node-4\n  public_address: 192.168.36.152\n  public_netmask: 255.255.255.0\n  role: primary-keystone\n  storage_address: 192.168.1.1\n  storage_netmask: 255.255.255.0\n  swift_zone: '4'\n  uid: '4'\n  user_node_name: Untitled (ea:68)\n- fqdn: node-4.domain.tld\n  internal_address: 192.168.0.3\n  internal_netmask: 255.255.255.0\n  name: node-4\n  public_address: 192.168.36.152\n  public_netmask: 255.255.255.0\n  role: primary-neutron\n  storage_address: 192.168.1.1\n  storage_netmask: 255.255.255.0\n  swift_zone: '4'\n  uid: '4'\n  user_node_name: Untitled (ea:68)\n- fqdn: node-4.domain.tld\n  internal_address: 192.168.0.3\n  internal_netmask: 255.255.255.0\n  name: node-4\n  public_address: 192.168.36.152\n  public_netmask: 255.255.255.0\n  role: primary-rabbitmq\n  storage_address: 192.168.1.1\n  storage_netmask: 255.255.255.0\n  swift_zone: '4'\n  uid: '4'\n  user_node_name: Untitled (ea:68)\nnova:\n  db_password: 1notRv9WqAyTCsKIx4KoZ6Z7\n  state_path: /var/lib/nova\n  user_password: uiAW7tFP1TmUKwSc9rZn5UPh\nnova_quota: false\nonline: true\nopenstack_version: mitaka-9.0\noperator_user:\n  authkeys: ''\n  homedir: /home/fueladmin\n  metadata:\n    group: general\n    label: Operating System Access\n    weight: 15\n  name: fueladmin\n  password: 9q20j4PeelboytJ9z5kTcW8W\n  sudo: 'ALL=(ALL) NOPASSWD: ALL'\nplugins: []\npropagate_task_deploy: false\nprovision:\n  codename: trusty\n  engine:\n    master_ip: 10.20.0.2\n    password: 8hOBmOlABdB4DDuX5XXhI0Sl\n    url: http://10.20.0.2:80/cobbler_api\n    username: cobbler\n  hostname: node-4.domain.tld\n  image_data:\n    /:\n      container: gzip\n      format: ext4\n      uri: http://10.20.0.2:8080/targetimages/env_1_ubuntu_1404_amd64.img.gz\n    /boot:\n      container: gzip\n      format: ext2\n      uri: http://10.20.0.2:8080/targetimages/env_1_ubuntu_1404_amd64-boot.img.gz\n  interfaces:\n    eth0:\n      dns_name: node-4.domain.tld\n      ip_address: 10.20.0.3\n      mac_address: 52:54:00:16:ea:68\n      netmask: 255.255.255.0\n      static: '0'\n    eth1:\n      mac_address: 52:54:00:4f:5a:5f\n      static: '0'\n    eth2:\n      mac_address: 52:54:00:56:0d:b1\n      static: '0'\n    eth3:\n      mac_address: 52:54:00:66:d7:8e\n      static: '0'\n  interfaces_extra:\n    eth0:\n      onboot: 'yes'\n      peerdns: 'no'\n    eth1:\n      onboot: 'no'\n      peerdns: 'no'\n    eth2:\n      onboot: 'no'\n      peerdns: 'no'\n    eth3:\n      onboot: 'no'\n      peerdns: 'no'\n  kernel_options:\n    netcfg/choose_interface: 52:54:00:16:ea:68\n    udevrules: 52:54:00:16:ea:68_eth0,52:54:00:4f:5a:5f_eth1,52:54:00:56:0d:b1_eth2,52:54:00:66:d7:8e_eth3\n  ks_meta:\n    admin_net: 10.20.0.0/24\n    auth_key: '\"\"'\n    authorized_keys:\n    - '\"ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQD5dzcY/wMTG7TFwNV2fakO9B6fRy9BpTW9Va4TRN+3KHQgV/5ZYqdFRcqjQU5EqFQR50ThOrTVWjO6lbqINhSqOVKJ0wpUkdB5Fd+ovevSs+VywQbVW6RBU+YE34mlUgsZ+UJ5K4vAWV2IIp0FHikJ3ehr2FQMvJb9B+l3SpNw7hjKCOQ9KHBzofMnaq9QqZyvjRchd7zmIrJO+DV+MQDxZ4AqmQBzCVXjQK3RJ2a9ulBVw7ypQ1qyHm2JDtWxrCoEXDEGYAKrVMxHPWXKOpHtVe0+1trIN6uWtLyDRmHvma4ApiiLCJFQo42KigWz//MB+duHLosGgtEwBIFDWOZp\n      root@xcloudos.domain.tld\"'\n    cloud_init_templates:\n      boothook: boothook_fuel_9.0_ubuntu.jinja2\n      cloud_config: cloud_config_fuel_9.0_ubuntu.jinja2\n      meta_data: meta_data_fuel_9.0_ubuntu.jinja2\n    fuel_version: '9.0'\n    gw: 10.20.0.2\n    image_data:\n      /:\n        container: gzip\n        format: ext4\n        uri: http://10.20.0.2:8080/targetimages/env_1_ubuntu_1404_amd64.img.gz\n      /boot:\n        container: gzip\n        format: ext2\n        uri: http://10.20.0.2:8080/targetimages/env_1_ubuntu_1404_amd64-boot.img.gz\n    install_log_2_syslog: 1\n    master_ip: 10.20.0.2\n    mco_auto_setup: 1\n    mco_connector: rabbitmq\n    mco_enable: 1\n    mco_host: 10.20.0.2\n    mco_identity: 4\n    mco_password: VVf88IhkApAJFpRxFSzvOc2X\n    mco_pskey: unset\n    mco_user: mcollective\n    mco_vhost: mcollective\n    pm_data:\n      kernel_params: console=tty0 net.ifnames=1 biosdevname=0 rootdelay=90 nomodeset\n      ks_spaces:\n      - bootable: true\n        extra: []\n        free_space: 81100\n        id: vda\n        name: vda\n        size: 81920\n        type: disk\n        volumes:\n        - size: 300\n          type: boot\n        - file_system: ext2\n          mount: /boot\n          name: Boot\n          size: 200\n          type: partition\n        - size: 0\n          type: lvm_meta_pool\n        - lvm_meta_size: 64\n          size: 24640\n          type: pv\n          vg: os\n        - lvm_meta_size: 64\n          size: 10304\n          type: pv\n          vg: logs\n        - lvm_meta_size: 64\n          size: 20544\n          type: pv\n          vg: mysql\n        - lvm_meta_size: 64\n          size: 11328\n          type: pv\n          vg: horizon\n        - lvm_meta_size: 64\n          size: 14604\n          type: pv\n          vg: image\n      - _allocate_size: min\n        id: os\n        label: Base System\n        min_size: 24576\n        type: vg\n        volumes:\n        - file_system: ext4\n          mount: /\n          name: root\n          size: 16384\n          type: lv\n        - file_system: swap\n          mount: swap\n          name: swap\n          size: 8192\n          type: lv\n      - _allocate_size: min\n        id: logs\n        label: Logs\n        min_size: 10240\n        type: vg\n        volumes:\n        - file_system: ext4\n          mount: /var/log\n          name: log\n          size: 10240\n          type: lv\n      - _allocate_size: all\n        id: image\n        label: Image Storage\n        min_size: 5120\n        type: vg\n        volumes:\n        - file_system: xfs\n          mount: /var/lib/glance\n          name: glance\n          size: 14540\n          type: lv\n      - _allocate_size: min\n        id: mysql\n        label: Mysql Database\n        min_size: 20480\n        type: vg\n        volumes:\n        - file_system: ext4\n          mount: /var/lib/mysql\n          name: root\n          size: 20480\n          type: lv\n      - _allocate_size: min\n        id: horizon\n        label: Horizon Temp Storage\n        min_size: 11264\n        type: vg\n        volumes:\n        - file_system: xfs\n          mount: /var/lib/horizon\n          name: horizontmp\n          size: 11264\n          type: lv\n    puppet_auto_setup: 1\n    puppet_enable: 0\n    puppet_master: localhost\n    repo_setup:\n      installer_initrd:\n        local: /var/www/nailgun/ubuntu/x86_64/images/initrd.gz\n        remote_relative: dists/trusty/main/installer-amd64/current/images/netboot/ubuntu-installer/amd64/initrd.gz\n      installer_kernel:\n        local: /var/www/nailgun/ubuntu/x86_64/images/linux\n        remote_relative: dists/trusty/main/installer-amd64/current/images/netboot/ubuntu-installer/amd64/linux\n      metadata:\n        always_editable: true\n        group: general\n        label: Repositories\n        weight: 50\n      repos:\n      - name: ubuntu\n        priority: null\n        section: main universe multiverse\n        suite: trusty\n        type: deb\n        uri: http://archive.ubuntu.com/ubuntu/\n      - name: ubuntu-updates\n        priority: null\n        section: main universe multiverse\n        suite: trusty-updates\n        type: deb\n        uri: http://archive.ubuntu.com/ubuntu/\n      - name: ubuntu-security\n        priority: null\n        section: main universe multiverse\n        suite: trusty-security\n        type: deb\n        uri: http://archive.ubuntu.com/ubuntu/\n      - name: mos\n        priority: 1050\n        section: main restricted\n        suite: mos9.0\n        type: deb\n        uri: http://10.20.0.2:8080/mitaka-9.0/ubuntu/x86_64\n      - name: mos-updates\n        priority: 1050\n        section: main restricted\n        suite: mos9.0-updates\n        type: deb\n        uri: http://mirror.fuel-infra.org/mos-repos/ubuntu/9.0/\n      - name: mos-security\n        priority: 1050\n        section: main restricted\n        suite: mos9.0-security\n        type: deb\n        uri: http://mirror.fuel-infra.org/mos-repos/ubuntu/9.0/\n      - name: mos-holdback\n        priority: 1100\n        section: main restricted\n        suite: mos9.0-holdback\n        type: deb\n        uri: http://mirror.fuel-infra.org/mos-repos/ubuntu/9.0/\n      - name: Auxiliary\n        priority: 1150\n        section: main restricted\n        suite: auxiliary\n        type: deb\n        uri: http://10.20.0.2:8080/mitaka-9.0/ubuntu/auxiliary\n    timezone: Etc/UTC\n    user_accounts:\n    - homedir: /home/fueladmin\n      name: fueladmin\n      password: 9q20j4PeelboytJ9z5kTcW8W\n      ssh_keys:\n      - ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQD5dzcY/wMTG7TFwNV2fakO9B6fRy9BpTW9Va4TRN+3KHQgV/5ZYqdFRcqjQU5EqFQR50ThOrTVWjO6lbqINhSqOVKJ0wpUkdB5Fd+ovevSs+VywQbVW6RBU+YE34mlUgsZ+UJ5K4vAWV2IIp0FHikJ3ehr2FQMvJb9B+l3SpNw7hjKCOQ9KHBzofMnaq9QqZyvjRchd7zmIrJO+DV+MQDxZ4AqmQBzCVXjQK3RJ2a9ulBVw7ypQ1qyHm2JDtWxrCoEXDEGYAKrVMxHPWXKOpHtVe0+1trIN6uWtLyDRmHvma4ApiiLCJFQo42KigWz//MB+duHLosGgtEwBIFDWOZp\n        root@xcloudos.domain.tld\n      sudo:\n      - 'ALL=(ALL) NOPASSWD: ALL'\n    - homedir: /var/lib/fuel\n      name: fuel\n      password: hDEwC5vK3FAM2PjxqrdJ5Kb0\n      ssh_keys:\n      - ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQD5dzcY/wMTG7TFwNV2fakO9B6fRy9BpTW9Va4TRN+3KHQgV/5ZYqdFRcqjQU5EqFQR50ThOrTVWjO6lbqINhSqOVKJ0wpUkdB5Fd+ovevSs+VywQbVW6RBU+YE34mlUgsZ+UJ5K4vAWV2IIp0FHikJ3ehr2FQMvJb9B+l3SpNw7hjKCOQ9KHBzofMnaq9QqZyvjRchd7zmIrJO+DV+MQDxZ4AqmQBzCVXjQK3RJ2a9ulBVw7ypQ1qyHm2JDtWxrCoEXDEGYAKrVMxHPWXKOpHtVe0+1trIN6uWtLyDRmHvma4ApiiLCJFQo42KigWz//MB+duHLosGgtEwBIFDWOZp\n        root@xcloudos.domain.tld\n      sudo:\n      - 'ALL=(ALL) NOPASSWD: ALL'\n    - homedir: /root\n      name: root\n      password: r00tme\n      ssh_keys:\n      - ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQD5dzcY/wMTG7TFwNV2fakO9B6fRy9BpTW9Va4TRN+3KHQgV/5ZYqdFRcqjQU5EqFQR50ThOrTVWjO6lbqINhSqOVKJ0wpUkdB5Fd+ovevSs+VywQbVW6RBU+YE34mlUgsZ+UJ5K4vAWV2IIp0FHikJ3ehr2FQMvJb9B+l3SpNw7hjKCOQ9KHBzofMnaq9QqZyvjRchd7zmIrJO+DV+MQDxZ4AqmQBzCVXjQK3RJ2a9ulBVw7ypQ1qyHm2JDtWxrCoEXDEGYAKrVMxHPWXKOpHtVe0+1trIN6uWtLyDRmHvma4ApiiLCJFQo42KigWz//MB+duHLosGgtEwBIFDWOZp\n        root@xcloudos.domain.tld\n  metadata:\n    group: general\n    label: Provision\n    restrictions:\n    - action: hide\n      condition: 'false'\n    weight: 80\n  method: image\n  name: node-4\n  name_servers: '\"10.20.0.2\"'\n  name_servers_search: '\"domain.tld\"'\n  netboot_enabled: '1'\n  packages:\n  - acl\n  - anacron\n  - bash-completion\n  - bridge-utils\n  - bsdmainutils\n  - build-essential\n  - cloud-init\n  - curl\n  - daemonize\n  - debconf-utils\n  - gdisk\n  - grub-pc\n  - hpsa-dkms\n  - hwloc\n  - i40e-dkms\n  - linux-firmware\n  - linux-firmware-nonfree\n  - linux-headers-generic-lts-trusty\n  - linux-image-generic-lts-trusty\n  - lvm2\n  - mcollective\n  - mdadm\n  - multipath-tools\n  - multipath-tools-boot\n  - nailgun-agent\n  - nailgun-mcagents\n  - network-checker\n  - ntp\n  - openssh-client\n  - openssh-server\n  - puppet\n  - python-amqp\n  - ruby-augeas\n  - ruby-ipaddress\n  - ruby-json\n  - ruby-netaddr\n  - ruby-openstack\n  - ruby-shadow\n  - ruby-stomp\n  - systemd-shim\n  - telnet\n  - ubuntu-minimal\n  - ubuntu-standard\n  - uuid-runtime\n  - vim\n  - virt-what\n  - vlan\n  - xcloud-init\n  power_address: 10.20.0.3\n  power_pass: /root/.ssh/bootstrap.rsa\n  power_type: ssh\n  power_user: root\n  profile: ubuntu_1404_x86_64\n  slave_name: node-4\n  uid: '4'\npublic_network_assignment:\n  assign_to_all_nodes: false\n  metadata:\n    group: network\n    label: Public network assignment\n    restrictions:\n    - action: hide\n      condition: cluster:net_provider != 'neutron'\n    weight: 10\npublic_ssl:\n  cert_data: ''\n  cert_source: self_signed\n  horizon: false\n  hostname: public.fuel.local\n  metadata:\n    group: security\n    label: Public TLS\n    weight: 110\n  services: false\npuppet:\n  manifests: rsync://10.20.0.2:/puppet/mitaka-9.0/manifests/\n  modules: rsync://10.20.0.2:/puppet/mitaka-9.0/modules/\npuppet_debug: true\nquantum: true\nquantum_settings:\n  L2:\n    base_mac: fa:16:3e:00:00:00\n    phys_nets:\n      physnet1:\n        bridge: br-floating\n        vlan_range: null\n      physnet2:\n        bridge: br-prv\n        vlan_range: 1000:1030\n    segmentation_type: vlan\n  L3:\n    use_namespaces: true\n  database:\n    passwd: tUdZnWImSt0BKUSeMRJB05os\n  default_floating_net: admin_floating_net\n  default_private_net: admin_internal_net\n  keystone:\n    admin_password: NZy11l1QLWs6QXtFMNpHpzMZ\n  metadata:\n    metadata_proxy_shared_secret: BBe6zzRryHjhrxwZKgTFgMW1\n  predefined_networks:\n    admin_floating_net:\n      L2:\n        network_type: flat\n        physnet: physnet1\n        router_ext: true\n        segment_id: null\n      L3:\n        enable_dhcp: false\n        floating:\n        - 192.168.36.190:192.168.36.200\n        gateway: 192.168.36.254\n        nameservers: []\n        subnet: 192.168.36.0/24\n      shared: false\n      tenant: admin\n    admin_internal_net:\n      L2:\n        network_type: vlan\n        physnet: physnet2\n        router_ext: false\n        segment_id: null\n      L3:\n        enable_dhcp: true\n        floating: null\n        gateway: 192.168.111.1\n        nameservers:\n        - 8.8.4.4\n        - 8.8.8.8\n        subnet: 192.168.111.0/24\n      shared: false\n      tenant: admin\nrabbit:\n  password: C0xPfRUuDI6Zx7xICwth8dkW\nrelease:\n  name: Mitaka on Ubuntu 14.04\n  operating_system: Ubuntu\n  version: mitaka-9.0\nrepo_setup:\n  installer_initrd:\n    local: /var/www/nailgun/ubuntu/x86_64/images/initrd.gz\n    remote_relative: dists/trusty/main/installer-amd64/current/images/netboot/ubuntu-installer/amd64/initrd.gz\n  installer_kernel:\n    local: /var/www/nailgun/ubuntu/x86_64/images/linux\n    remote_relative: dists/trusty/main/installer-amd64/current/images/netboot/ubuntu-installer/amd64/linux\n  metadata:\n    always_editable: true\n    group: general\n    label: Repositories\n    weight: 50\n  repos:\n  - name: ubuntu\n    priority: null\n    section: main universe multiverse\n    suite: trusty\n    type: deb\n    uri: http://archive.ubuntu.com/ubuntu/\n  - name: ubuntu-updates\n    priority: null\n    section: main universe multiverse\n    suite: trusty-updates\n    type: deb\n    uri: http://archive.ubuntu.com/ubuntu/\n  - name: ubuntu-security\n    priority: null\n    section: main universe multiverse\n    suite: trusty-security\n    type: deb\n    uri: http://archive.ubuntu.com/ubuntu/\n  - name: mos\n    priority: 1050\n    section: main restricted\n    suite: mos9.0\n    type: deb\n    uri: http://10.20.0.2:8080/mitaka-9.0/ubuntu/x86_64\n  - name: mos-updates\n    priority: 1050\n    section: main restricted\n    suite: mos9.0-updates\n    type: deb\n    uri: http://mirror.fuel-infra.org/mos-repos/ubuntu/9.0/\n  - name: mos-security\n    priority: 1050\n    section: main restricted\n    suite: mos9.0-security\n    type: deb\n    uri: http://mirror.fuel-infra.org/mos-repos/ubuntu/9.0/\n  - name: mos-holdback\n    priority: 1100\n    section: main restricted\n    suite: mos9.0-holdback\n    type: deb\n    uri: http://mirror.fuel-infra.org/mos-repos/ubuntu/9.0/\n  - name: Auxiliary\n    priority: 1150\n    section: main restricted\n    suite: auxiliary\n    type: deb\n    uri: http://10.20.0.2:8080/mitaka-9.0/ubuntu/auxiliary\nresume_guests_state_on_host_boot: true\nroles:\n- primary-controller\n- primary-database\n- primary-keystone\n- primary-neutron\n- primary-rabbitmq\nrun_ping_checker: true\nsahara:\n  db_password: vhJ5wvhJBPwnIFMJBBkLtAc8\n  enabled: false\n  user_password: p2eoH89EjeUAA2IY8kUqLEoV\nsecurity_groups: iptables_hybrid\nservice_user:\n  homedir: /var/lib/fuel\n  metadata:\n    group: general\n    label: Service user account\n    restrictions:\n    - action: hide\n      condition: 'true'\n    weight: 10\n  name: fuel\n  password: hDEwC5vK3FAM2PjxqrdJ5Kb0\n  root_password: r00tme\n  sudo: 'ALL=(ALL) NOPASSWD: ALL'\nstatus: discover\nstorage:\n  admin_key: AQA+uAJZAAAAABAAbp0qUtuS/8sInG2CW5OGzg==\n  auth_s3_keystone_ceph: false\n  bootstrap_osd_key: AQA+uAJZAAAAABAAmUf1D3TPPYMKTpMbb3HsQA==\n  ephemeral_ceph: false\n  fsid: de123aba-9956-45ae-ad2e-bae734c39927\n  images_ceph: false\n  images_vcenter: false\n  metadata:\n    group: storage\n    label: Storage Backends\n    weight: 60\n  mon_key: AQA+uAJZAAAAABAApt7MhcuRbVRypFOk/Xmu2g==\n  objects_ceph: false\n  osd_pool_size: '3'\n  per_pool_pg_nums:\n    .rgw: 128\n    backups: 128\n    compute: 128\n    default_pg_num: 128\n    images: 128\n    volumes: 128\n  pg_num: 128\n  radosgw_key: AQA+uAJZAAAAABAASYiav0Eyt0sgTsxqPppi5g==\n  volumes_block_device: false\n  volumes_ceph: false\n  volumes_lvm: true\nstorage_network_range: 192.168.1.0/24\nswift:\n  user_password: Ox5NysYCAB6jBAjmiLrflpiB\nsyslog:\n  metadata:\n    enabled: false\n    group: logging\n    label: Syslog\n    toggleable: true\n    weight: 50\n  syslog_port: '514'\n  syslog_server: ''\n  syslog_transport: tcp\ntask_deploy: true\ntest_vm_image:\n  container_format: bare\n  disk_format: qcow2\n  glance_properties: ''\n  img_name: TestVM\n  img_path: /usr/share/cirros-testvm/cirros-x86_64-disk.img\n  min_ram: 64\n  os_name: cirros\n  properties: {}\n  public: 'true'\nuid: '4'\nuse_cow_images: true\nuse_vcenter: false\nuser_node_name: Untitled (ea:68)\nvms_conf: []\nworkloads_collector:\n  create_user: false\n  enabled: true\n  metadata:\n    group: general\n    label: Workloads Collector User\n    restrictions:\n    - action: hide\n      condition: 'true'\n    weight: 10\n  password: 3Ee7uZ7MuS5yhDmDvkjh1Zh8\n  tenant: services\n  username: fuel_stats_user\n",
                            "cwd": "/",
                            "permissions": "0640"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "override_configuration"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "pre_deployment_start"
                            }
                        ],
                        "type": "upload_file",
                        "id": "upload_configuration"
                    },
                    {
                        "type": "skipped",
                        "fail_on_error": false,
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "firewall"
                            },
                            {
                                "node_id": "4",
                                "name": "ssl-add-trust-chain"
                            }
                        ],
                        "id": "ssl-dns-setup",
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "hosts"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/openstack-network/keystone.pp",
                            "timeout": 1800,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-keystone"
                            }
                        ],
                        "id": "neutron-keystone",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "openstack-network-end"
                            }
                        ],
                        "type": "puppet"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/logging/logging.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "setup_repositories"
                            },
                            {
                                "node_id": "4",
                                "name": "globals"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet",
                        "id": "logging"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/limits/limits.pp",
                            "timeout": 120,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "logging"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "tools"
                            }
                        ],
                        "type": "puppet",
                        "id": "limits"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/openstack-controller/keystone.pp",
                            "timeout": 1800,
                            "cwd": "/"
                        },
                        "type": "puppet",
                        "id": "nova-keystone",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "primary-openstack-controller"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-keystone"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/hosts/hosts.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "upload_nodes_info"
                            },
                            {
                                "node_id": "4",
                                "name": "copy_deleted_nodes"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "post_deployment_end"
                            }
                        ],
                        "type": "puppet",
                        "id": "update_hosts"
                    },
                    {
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-keystone"
                            }
                        ],
                        "id": "ironic-keystone",
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "ironic-api"
                            }
                        ],
                        "type": "skipped"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/netconfig/connectivity_tests.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "netconfig"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "hosts"
                            },
                            {
                                "node_id": "4",
                                "name": "firewall"
                            }
                        ],
                        "type": "puppet",
                        "id": "connectivity_tests"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/heat/heat.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "memcached"
                            },
                            {
                                "node_id": "4",
                                "name": "heat-db"
                            },
                            {
                                "node_id": "4",
                                "name": "heat-keystone"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-rabbitmq"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-openstack-controller"
                            }
                        ],
                        "id": "primary-heat",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/virtual_ips/conntrackd.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-cluster"
                            },
                            {
                                "node_id": "4",
                                "name": "cluster_health"
                            },
                            {
                                "node_id": "4",
                                "name": "cluster-vrouter"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-cluster-haproxy"
                            },
                            {
                                "node_id": "4",
                                "name": "cluster"
                            },
                            {
                                "node_id": "4",
                                "name": "virtual_ips"
                            }
                        ],
                        "id": "conntrackd",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet"
                    },
                    {
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-database"
                            }
                        ],
                        "id": "sahara-db",
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "sahara"
                            }
                        ],
                        "type": "skipped"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/horizon/horizon.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "memcached"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-openstack-controller"
                            }
                        ],
                        "id": "horizon",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/hiera/hiera.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "rsync_core_puppet"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "pre_deployment_start"
                            }
                        ],
                        "type": "puppet",
                        "id": "pre_hiera_config"
                    },
                    {
                        "type": "skipped",
                        "fail_on_error": false,
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "cluster"
                            },
                            {
                                "node_id": "4",
                                "name": "virtual_ips"
                            },
                            {
                                "node_id": null,
                                "name": "deploy_start"
                            }
                        ],
                        "id": "restart-haproxy",
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ]
                    },
                    {
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-cluster-haproxy"
                            },
                            {
                                "node_id": null,
                                "name": "deploy_start"
                            }
                        ],
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "skipped",
                        "id": "openstack-haproxy-ceilometer"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/openstack-network/common-config.pp",
                            "timeout": 1800,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "openstack-network-start"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "openstack-network-end"
                            }
                        ],
                        "type": "puppet",
                        "id": "openstack-network-common-config"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/firewall/firewall.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "netconfig"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet",
                        "id": "firewall"
                    },
                    {
                        "parameters": {
                            "files": [
                                {
                                    "src": "/etc/fuel/cluster/1/deleted_nodes.yaml",
                                    "dst": "/etc/hiera/deleted_nodes.yaml"
                                }
                            ],
                            "dir_permissions": "0750",
                            "cwd": "/",
                            "permissions": "0640"
                        },
                        "requires": [
                            {
                                "node_id": "master",
                                "name": "generate_deleted_nodes"
                            }
                        ],
                        "id": "copy_deleted_nodes",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "pre_deployment_end"
                            }
                        ],
                        "type": "copy_files"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/apache/apache.pp",
                            "timeout": 1200,
                            "cwd": "/"
                        },
                        "type": "puppet",
                        "id": "apache",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "primary-keystone"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "netconfig"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/globals/globals.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "hiera"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet",
                        "id": "globals"
                    },
                    {
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-keystone"
                            }
                        ],
                        "id": "aodh-keystone",
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "aodh"
                            }
                        ],
                        "type": "skipped"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/glance/glance.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "type": "puppet",
                        "id": "glance",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "primary-openstack-controller"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-database"
                            },
                            {
                                "node_id": "4",
                                "name": "glance-keystone"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-haproxy"
                            },
                            {
                                "node_id": "4",
                                "name": "glance-db"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-rabbitmq"
                            }
                        ]
                    },
                    {
                        "type": "skipped",
                        "fail_on_error": false,
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "setup_repositories"
                            }
                        ],
                        "id": "prepare_symlinks",
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "pkg_upgrade"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/openstack-haproxy/openstack-haproxy.pp",
                            "timeout": 300,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "openstack-haproxy-mysqld"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-haproxy-ceilometer"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-haproxy-stats"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-haproxy-ironic"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-haproxy-radosgw"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-haproxy-glance"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-haproxy-keystone"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-haproxy-neutron"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-haproxy-heat"
                            },
                            {
                                "node_id": null,
                                "name": "deploy_start"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-haproxy-murano"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-haproxy-sahara"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-haproxy-nova"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-haproxy-cinder"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-haproxy-aodh"
                            },
                            {
                                "node_id": "4",
                                "name": "restart-haproxy"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-haproxy-horizon"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-haproxy-swift"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet",
                        "id": "openstack-haproxy"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/cgroups/cgroups.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": null,
                                "name": "post_deployment_start"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "post_deployment_end"
                            }
                        ],
                        "type": "puppet",
                        "id": "cgroups"
                    },
                    {
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-keystone"
                            }
                        ],
                        "id": "murano-cfapi-keystone",
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "murano-cfapi"
                            }
                        ],
                        "type": "skipped"
                    },
                    {
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "aodh-db"
                            },
                            {
                                "node_id": "4",
                                "name": "aodh-keystone"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-haproxy"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-rabbitmq"
                            }
                        ],
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "ceilometer-controller"
                            }
                        ],
                        "type": "skipped",
                        "id": "aodh"
                    },
                    {
                        "requires": [
                            {
                                "node_id": null,
                                "name": "post_deployment_start"
                            }
                        ],
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "ceph_ready_check"
                            }
                        ],
                        "type": "skipped",
                        "id": "ceph_create_pools"
                    },
                    {
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-cluster-haproxy"
                            },
                            {
                                "node_id": null,
                                "name": "deploy_start"
                            }
                        ],
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "skipped",
                        "id": "openstack-haproxy-ironic"
                    },
                    {
                        "type": "skipped",
                        "fail_on_error": false,
                        "requires": [
                            {
                                "node_id": null,
                                "name": "pre_deployment_start"
                            }
                        ],
                        "id": "clear_nodes_info",
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "pre_deployment_end"
                            }
                        ]
                    },
                    {
                        "type": "skipped",
                        "fail_on_error": false,
                        "requires": [
                            {
                                "node_id": null,
                                "name": "post_deployment_start"
                            }
                        ],
                        "id": "openstack-network-routers-ha",
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "post_deployment_end"
                            }
                        ]
                    },
                    {
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "upload_cirros"
                            }
                        ],
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "post_deployment_end"
                            }
                        ],
                        "type": "skipped",
                        "id": "upload_murano_package"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/glance/db.pp",
                            "timeout": 1800,
                            "cwd": "/"
                        },
                        "type": "puppet",
                        "id": "glance-db",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "glance"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-database"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/openstack-network/db.pp",
                            "timeout": 1800,
                            "cwd": "/"
                        },
                        "type": "puppet",
                        "id": "neutron-db",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "openstack-network-end"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-database"
                            }
                        ]
                    },
                    {
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "enable_quorum"
                            },
                            {
                                "node_id": "4",
                                "name": "enable_rados"
                            }
                        ],
                        "id": "ironic_upload_images",
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "post_deployment_end"
                            }
                        ],
                        "type": "skipped"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/astute/create_resources.pp",
                            "timeout": 300,
                            "cwd": "/"
                        },
                        "type": "puppet",
                        "id": "create_resources",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "post_deployment_end"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": null,
                                "name": "post_deployment_start"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/swift/rebalance_cronjob.pp",
                            "timeout": 300,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "swift-proxy_storage"
                            }
                        ],
                        "id": "swift-rebalance-cron",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/ceph/mon.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "openstack-cinder"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-openstack-controller"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            },
                            {
                                "node_id": "4",
                                "name": "controller_remaining_tasks"
                            }
                        ],
                        "type": "puppet",
                        "id": "primary-ceph-mon"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/openstack-haproxy/openstack-haproxy-stats.pp",
                            "timeout": 300,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-cluster-haproxy"
                            },
                            {
                                "node_id": null,
                                "name": "deploy_start"
                            }
                        ],
                        "id": "openstack-haproxy-stats",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet"
                    },
                    {
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "ironic-keystone"
                            },
                            {
                                "node_id": "4",
                                "name": "ironic-db"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-haproxy"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-rabbitmq"
                            }
                        ],
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "primary-openstack-controller"
                            }
                        ],
                        "type": "skipped",
                        "id": "ironic-api"
                    },
                    {
                        "type": "skipped",
                        "fail_on_error": false,
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-ceph-mon"
                            },
                            {
                                "node_id": "4",
                                "name": "apache"
                            }
                        ],
                        "id": "primary-ceph-radosgw",
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            },
                            {
                                "node_id": "4",
                                "name": "controller_remaining_tasks"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/dns/dns-client.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": null,
                                "name": "post_deployment_start"
                            }
                        ],
                        "fail_on_error": true,
                        "type": "puppet",
                        "id": "dns-client"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/cluster-vrouter/cluster-vrouter.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-cluster"
                            },
                            {
                                "node_id": "4",
                                "name": "cluster"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "virtual_ips"
                            }
                        ],
                        "type": "puppet",
                        "id": "cluster-vrouter"
                    },
                    {
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-rabbitmq"
                            }
                        ],
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "murano"
                            }
                        ],
                        "type": "skipped",
                        "id": "murano-rabbitmq"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/api-proxy/api-proxy.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "apache"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            },
                            {
                                "node_id": "4",
                                "name": "controller_remaining_tasks"
                            }
                        ],
                        "type": "puppet",
                        "id": "api-proxy"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/cluster/health.pp",
                            "timeout": 600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-cluster"
                            },
                            {
                                "node_id": "4",
                                "name": "cluster"
                            },
                            {
                                "node_id": "4",
                                "name": "cluster-vrouter"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-cluster-haproxy"
                            },
                            {
                                "node_id": "4",
                                "name": "cluster_health"
                            }
                        ],
                        "id": "cluster_health",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/heat/keystone.pp",
                            "timeout": 1800,
                            "cwd": "/"
                        },
                        "type": "puppet",
                        "id": "heat-keystone",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "primary-heat"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-keystone"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/openstack-haproxy/openstack-haproxy-horizon.pp",
                            "timeout": 300,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-cluster-haproxy"
                            },
                            {
                                "node_id": null,
                                "name": "deploy_start"
                            }
                        ],
                        "id": "openstack-haproxy-horizon",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet"
                    },
                    {
                        "type": "skipped",
                        "id": "openstack-network-start",
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "openstack-network-common-config"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "netconfig"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-rabbitmq"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-openstack-controller"
                            },
                            {
                                "node_id": "4",
                                "name": "neutron-keystone"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-haproxy"
                            },
                            {
                                "node_id": "4",
                                "name": "neutron-db"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/fuel_pkgs/setup_repositories.pp",
                            "timeout": 600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "hiera"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "fuel_pkgs"
                            }
                        ],
                        "type": "puppet",
                        "id": "setup_repositories"
                    },
                    {
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-database"
                            }
                        ],
                        "id": "murano-db",
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "murano"
                            }
                        ],
                        "type": "skipped"
                    },
                    {
                        "parameters": {
                            "files": [
                                {
                                    "src": "/var/lib/fuel/keys/1/ceph/ceph.pub",
                                    "dst": "/var/lib/astute/ceph/ceph.pub"
                                },
                                {
                                    "src": "/var/lib/fuel/keys/1/ceph/ceph",
                                    "dst": "/var/lib/astute/ceph/ceph"
                                }
                            ],
                            "dir_permissions": "0700",
                            "cwd": "/",
                            "permissions": "0600"
                        },
                        "requires": [
                            {
                                "node_id": "master",
                                "name": "generate_keys_ceph"
                            }
                        ],
                        "id": "copy_keys_ceph",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "pre_deployment_end"
                            }
                        ],
                        "type": "copy_files"
                    },
                    {
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "hosts"
                            },
                            {
                                "node_id": "4",
                                "name": "firewall"
                            },
                            {
                                "node_id": null,
                                "name": "deploy_start"
                            }
                        ],
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "skipped",
                        "id": "cluster"
                    },
                    {
                        "type": "skipped",
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "controller_remaining_tasks"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "openstack-network-end"
                            },
                            {
                                "node_id": "4",
                                "name": "sahara-db"
                            },
                            {
                                "node_id": "4",
                                "name": "sahara-keystone"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-rabbitmq"
                            },
                            {
                                "node_id": "4",
                                "name": "horizon"
                            }
                        ],
                        "id": "sahara"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/fuel_pkgs/fuel_pkgs.pp",
                            "timeout": 600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "setup_repositories"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "globals"
                            }
                        ],
                        "type": "puppet",
                        "id": "fuel_pkgs"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/swift/keystone.pp",
                            "timeout": 1800,
                            "cwd": "/"
                        },
                        "type": "puppet",
                        "id": "swift-keystone",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "swift-proxy_storage"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-keystone"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/virtual_ips/public_vip_ping.pp",
                            "timeout": 120,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": null,
                                "name": "post_deployment_start"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "post_deployment_end"
                            }
                        ],
                        "type": "puppet",
                        "id": "primary_public_vip_ping"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/netconfig/hiera_default_route.pp",
                            "timeout": 120,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "tools"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "netconfig"
                            }
                        ],
                        "type": "puppet",
                        "id": "hiera_default_route"
                    },
                    {
                        "type": "skipped",
                        "fail_on_error": false,
                        "requires": [
                            {
                                "node_id": null,
                                "name": "post_deployment_start"
                            }
                        ],
                        "id": "upload_nodes_info"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/openstack-haproxy/openstack-haproxy-glance.pp",
                            "timeout": 300,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-cluster-haproxy"
                            },
                            {
                                "node_id": null,
                                "name": "deploy_start"
                            }
                        ],
                        "id": "openstack-haproxy-glance",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet"
                    },
                    {
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-heat"
                            },
                            {
                                "node_id": "4",
                                "name": "murano-keystone"
                            },
                            {
                                "node_id": "4",
                                "name": "murano-db"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-rabbitmq"
                            },
                            {
                                "node_id": "4",
                                "name": "horizon"
                            }
                        ],
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            },
                            {
                                "node_id": "4",
                                "name": "controller_remaining_tasks"
                            }
                        ],
                        "type": "skipped",
                        "id": "murano"
                    },
                    {
                        "type": "skipped",
                        "fail_on_error": false,
                        "requires": [
                            {
                                "node_id": null,
                                "name": "post_deployment_start"
                            }
                        ],
                        "id": "ceph_ready_check",
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "upload_cirros"
                            },
                            {
                                "node_id": "4",
                                "name": "enable_rados"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "cmd": "ruby /etc/puppet/modules/osnailyfacter/modular/astute/enable_quorum.rb",
                            "cwd": "/",
                            "timeout": 180
                        },
                        "type": "shell",
                        "id": "enable_quorum",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "post_deployment_end"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": null,
                                "name": "post_deployment_start"
                            },
                            {
                                "node_id": "4",
                                "name": "ntp-server"
                            },
                            {
                                "node_id": "4",
                                "name": "dns-client"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "files": [
                                {
                                    "src": "/etc/fuel/cluster/1/old_admin_user.yaml",
                                    "dst": "/etc/hiera/old_admin_user.yaml"
                                }
                            ],
                            "dir_permissions": "0700",
                            "cwd": "/",
                            "permissions": "0600"
                        },
                        "type": "copy_files",
                        "id": "copy_changed_admin_user",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "pre_deployment_end"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "master",
                                "name": "generate_changed_admin_user"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/openstack-haproxy/openstack-haproxy-nova.pp",
                            "timeout": 300,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-cluster-haproxy"
                            },
                            {
                                "node_id": null,
                                "name": "deploy_start"
                            }
                        ],
                        "id": "openstack-haproxy-nova",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "strategy": {
                                "amount": 6,
                                "type": "parallel"
                            },
                            "cwd": "/",
                            "timeout": 3600,
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/database/database.pp"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-cluster"
                            },
                            {
                                "node_id": "4",
                                "name": "cluster"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-haproxy"
                            },
                            {
                                "node_id": null,
                                "name": "deploy_start"
                            }
                        ],
                        "id": "primary-database",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "primary-openstack-controller"
                            }
                        ],
                        "type": "puppet"
                    },
                    {
                        "type": "skipped",
                        "fail_on_error": false,
                        "requires": [
                            {
                                "node_id": null,
                                "name": "post_deployment_start"
                            }
                        ],
                        "id": "vcenter_compute_zones_create",
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "post_deployment_end"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/openstack-haproxy/openstack-haproxy-cinder.pp",
                            "timeout": 300,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-cluster-haproxy"
                            },
                            {
                                "node_id": null,
                                "name": "deploy_start"
                            }
                        ],
                        "id": "openstack-haproxy-cinder",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/ntp/ntp-server.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "dns-client"
                            }
                        ],
                        "fail_on_error": true,
                        "type": "puppet",
                        "id": "ntp-server"
                    },
                    {
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-keystone"
                            }
                        ],
                        "id": "murano-keystone",
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "murano"
                            }
                        ],
                        "type": "skipped"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/swift/proxy_storage.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "swift-keystone"
                            },
                            {
                                "node_id": "4",
                                "name": "glance"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-rabbitmq"
                            },
                            {
                                "node_id": "4",
                                "name": "glance-db"
                            },
                            {
                                "node_id": "4",
                                "name": "memcached"
                            },
                            {
                                "node_id": "4",
                                "name": "glance-keystone"
                            },
                            {
                                "node_id": "4",
                                "name": "ceilometer-controller"
                            }
                        ],
                        "id": "swift-proxy_storage",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            },
                            {
                                "node_id": "4",
                                "name": "controller_remaining_tasks"
                            }
                        ],
                        "type": "puppet"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/openstack-network/agents/dhcp.pp",
                            "timeout": 1800,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "openstack-network-common-config"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-rabbitmq"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-openstack-network-server-config"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-network-start"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-openstack-network-plugins-l2"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-network-server-nova"
                            }
                        ],
                        "id": "primary-openstack-network-agents-dhcp",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "openstack-network-end"
                            }
                        ],
                        "type": "puppet"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/osnailyfacter/modular/openstack-haproxy/openstack-haproxy-heat.pp",
                            "timeout": 300,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-cluster-haproxy"
                            },
                            {
                                "node_id": null,
                                "name": "deploy_start"
                            }
                        ],
                        "id": "openstack-haproxy-heat",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/openstack-controller/openstack-controller.pp",
                            "timeout": 3600,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "nova-keystone"
                            },
                            {
                                "node_id": "4",
                                "name": "memcached"
                            },
                            {
                                "node_id": "4",
                                "name": "nova-db"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-haproxy"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-rabbitmq"
                            }
                        ],
                        "id": "primary-openstack-controller",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "type": "puppet"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/openstack-cinder/openstack-cinder.pp",
                            "timeout": 1200,
                            "cwd": "/"
                        },
                        "type": "puppet",
                        "id": "openstack-cinder",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-keystone"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-rabbitmq"
                            },
                            {
                                "node_id": "4",
                                "name": "hosts"
                            },
                            {
                                "node_id": "4",
                                "name": "firewall"
                            },
                            {
                                "node_id": "4",
                                "name": "cinder-keystone"
                            },
                            {
                                "node_id": "4",
                                "name": "cinder-db"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/keystone/db.pp",
                            "timeout": 1800,
                            "cwd": "/"
                        },
                        "type": "puppet",
                        "id": "keystone-db",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "primary-keystone"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "primary-database"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "retries": 10,
                            "cmd": "timeout -s9 40 ntpdate -u -v -s $(awk '/^server/ { if ($2 !~ /127\\.127\\.[0-9]+\\.[0-9]+/) {ORS=\" \"; print $2}}' /etc/ntp.conf)",
                            "cwd": "/",
                            "timeout": 300,
                            "interval": 30
                        },
                        "requires": [
                            {
                                "node_id": null,
                                "name": "pre_deployment_start"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "pre_deployment_end"
                            }
                        ],
                        "type": "shell",
                        "id": "sync_time"
                    },
                    {
                        "parameters": {
                            "cmd": "ln -sf /etc/fuel/cluster/1/astute.yaml /etc/astute.yaml",
                            "cwd": "/",
                            "timeout": 180
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "upload_configuration"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "pre_deployment_start"
                            }
                        ],
                        "type": "shell",
                        "id": "configuration_symlink"
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/openstack-network/server-nova.pp",
                            "timeout": 1800,
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "openstack-network-common-config"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-openstack-network-server-config"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-network-start"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "openstack-network-end"
                            }
                        ],
                        "type": "puppet",
                        "id": "openstack-network-server-nova"
                    },
                    {
                        "requires": [
                            {
                                "node_id": "master",
                                "name": "generate_haproxy_keys"
                            }
                        ],
                        "fail_on_error": false,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "pre_deployment_end"
                            }
                        ],
                        "type": "skipped",
                        "id": "copy_haproxy_keys"
                    },
                    {
                        "type": "skipped",
                        "fail_on_error": false,
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "setup_repositories"
                            }
                        ],
                        "id": "pkg_upgrade",
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "fuel_pkgs"
                            }
                        ]
                    },
                    {
                        "parameters": {
                            "puppet_modules": "/etc/puppet/modules",
                            "puppet_manifest": "/etc/puppet/modules/openstack_tasks/examples/openstack-network/networks.pp",
                            "timeout": 1800,
                            "cwd": "/"
                        },
                        "type": "puppet",
                        "id": "openstack-network-networks",
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "openstack-network-end"
                            }
                        ],
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "openstack-network-common-config"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-openstack-network-server-config"
                            },
                            {
                                "node_id": "4",
                                "name": "openstack-network-start"
                            },
                            {
                                "node_id": "4",
                                "name": "primary-openstack-network-plugins-l2"
                            }
                        ]
                    },
                    {
                        "type": "skipped",
                        "fail_on_error": false,
                        "requires": [
                            {
                                "node_id": "4",
                                "name": "ssl-keys-saving"
                            },
                            {
                                "node_id": "4",
                                "name": "firewall"
                            }
                        ],
                        "id": "ssl-add-trust-chain",
                        "required_for": [
                            {
                                "node_id": "4",
                                "name": "hosts"
                            }
                        ]
                    }
                ],
                "null": [
                    {
                        "requires": [
                            {
                                "node_id": null,
                                "name": "deploy_end"
                            }
                        ],
                        "fail_on_error": false,
                        "type": "skipped",
                        "id": "post_deployment_start"
                    },
                    {
                        "requires": [
                            {
                                "node_id": null,
                                "name": "pre_deployment_end"
                            }
                        ],
                        "fail_on_error": false,
                        "type": "skipped",
                        "id": "deploy_start"
                    },
                    {
                        "requires": [
                            {
                                "node_id": null,
                                "name": "pre_deployment_start"
                            }
                        ],
                        "fail_on_error": false,
                        "type": "skipped",
                        "id": "pre_deployment_end"
                    },
                    {
                        "fail_on_error": false,
                        "type": "skipped",
                        "id": "pre_deployment_start"
                    },
                    {
                        "requires": [
                            {
                                "node_id": null,
                                "name": "post_deployment_start"
                            }
                        ],
                        "fail_on_error": false,
                        "type": "skipped",
                        "id": "post_deployment_end"
                    },
                    {
                        "requires": [
                            {
                                "node_id": null,
                                "name": "deploy_start"
                            }
                        ],
                        "fail_on_error": false,
                        "type": "skipped",
                        "id": "deploy_end"
                    }
                ],
                "master": [
                    {
                        "parameters": {
                            "cmd": "sh /etc/puppet/modules/osnailyfacter/modular/astute/generate_keys.sh -i 1 -s 'ceph' -p /var/lib/fuel/keys/",
                            "cwd": "/",
                            "timeout": 180
                        },
                        "requires": [
                            {
                                "node_id": null,
                                "name": "pre_deployment_start"
                            }
                        ],
                        "fail_on_error": true,
                        "type": "shell",
                        "id": "generate_keys_ceph"
                    },
                    {
                        "type": "skipped",
                        "fail_on_error": false,
                        "requires": [
                            {
                                "node_id": null,
                                "name": "pre_deployment_start"
                            }
                        ],
                        "id": "generate_haproxy_keys"
                    },
                    {
                        "parameters": {
                            "path": "/etc/fuel/cluster/1/old_admin_user.yaml",
                            "data": "old_access: {}\n",
                            "cwd": "/"
                        },
                        "requires": [
                            {
                                "node_id": "master",
                                "name": "upload_configuration"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "pre_deployment_end"
                            }
                        ],
                        "type": "upload_file",
                        "id": "generate_changed_admin_user"
                    },
                    {
                        "parameters": {
                            "path": "/etc/fuel/cluster/1/deleted_nodes.yaml",
                            "dir_permissions": "0750",
                            "data": "deleted_nodes: null\n",
                            "cwd": "/",
                            "permissions": "0640"
                        },
                        "requires": [
                            {
                                "node_id": "master",
                                "name": "upload_configuration"
                            }
                        ],
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "pre_deployment_end"
                            }
                        ],
                        "type": "upload_file",
                        "id": "generate_deleted_nodes"
                    },
                    {
                        "parameters": {
                            "cmd": "sh /etc/puppet/modules/osnailyfacter/modular/astute/generate_keys.sh -p /var/lib/fuel/keys/ -i 1 -o 'mongodb' -s 'neutron nova mysql' -f '0 1'",
                            "cwd": "/",
                            "timeout": 180
                        },
                        "requires": [
                            {
                                "node_id": null,
                                "name": "pre_deployment_start"
                            }
                        ],
                        "fail_on_error": true,
                        "type": "shell",
                        "id": "generate_keys"
                    },
                    {
                        "parameters": {
                            "dir_permissions": "0750",
                            "timeout": 180,
                            "path": "/etc/fuel/cluster/1/astute.yaml",
                            "data": "access:\n  email: admin@localhost\n  metadata:\n    group: general\n    label: OpenStack Access\n    weight: 10\n  password: admin\n  tenant: admin\n  user: admin\naodh:\n  db_password: QAKwUwho9BHYfTMyfOG2WnyZ\n  user_password: xz8gSdAkeIe7djhGN1BOr0gn\nauth_key: ''\nauto_assign_floating_ip: false\nbase_syslog:\n  syslog_port: '514'\n  syslog_server: 10.20.0.2\nceilometer:\n  db_password: 8tEYmdeKgsN3Atwk5idQonY0\n  enabled: false\n  metering_secret: QargkI39hic5U5lWZ0zPlSSU\n  user_password: DxBTOrMG0RT6gfgkAiWAWXdn\ncgroups:\n  metadata:\n    always_editable: true\n    group: general\n    label: Cgroups conguration for services\n    restrictions:\n    - action: hide\n      condition: 'true'\n    weight: 90\ncinder:\n  db_password: C2QsaX7mybOsScjnP84yB0o6\n  fixed_key: dc98130bd65d926c6c6d76408e1607bc871b6f23f4cbbe70bde0ee2da1bba647\n  user_password: 3rVZf2gQNwN14aP9jATCAQlA\ncluster:\n  fuel_version: '9.0'\n  id: 1\n  mode: ha_compact\n  name: test-env-kvm-default\n  status: deployment\ncobbler:\n  profile: ubuntu_1404_x86_64\ncorosync:\n  group: 226.94.1.1\n  metadata:\n    group: general\n    label: Corosync\n    restrictions:\n    - action: hide\n      condition: 'true'\n    weight: 50\n  port: '12000'\n  verified: false\ndebug: false\ndeployed_before:\n  value: false\ndeployment_id: 1\ndeployment_mode: ha_compact\nexternal_dns:\n  dns_list: null\n  metadata:\n    group: network\n    label: Host OS DNS Servers\n    weight: 30\nexternal_mongo:\n  hosts_ip: ''\n  metadata:\n    group: openstack_services\n    label: External MongoDB\n    restrictions:\n    - action: hide\n      condition: settings:additional_components.mongo.value == false\n      message: Ceilometer and MongoDB are not enabled on the Additional Components\n        section\n    weight: 30\n  mongo_db_name: ceilometer\n  mongo_password: ceilometer\n  mongo_replset: ''\n  mongo_user: ceilometer\nexternal_ntp:\n  metadata:\n    group: network\n    label: Host OS NTP Servers\n    weight: 40\n  ntp_list:\n  - 0.fuel.pool.ntp.org\n  - 1.fuel.pool.ntp.org\n  - 2.fuel.pool.ntp.org\nfuel_version: '9.0'\nglance:\n  db_password: XVyVtsbNI6iAtfzFblvu91Tz\n  user_password: ym4tpW1WUqvgYTvXWJT4kNYb\nglance_glare:\n  user_password: Qxv2ITExQZshZtgTf5sGH0jD\nheat:\n  auth_encryption_key: 754ce969bb3a3f5c7d208cce18655cdc\n  db_password: 4WzfoHZdjW7YLtUvYY1z6fsU\n  enabled: true\n  rabbit_password: LVzQQM48AxY65m86l0fG1wwk\n  user_password: v05jnvd9pQHVt1pufEhLWkFs\nhorizon:\n  secret_key: e8555623051accac68498e324b81c2ec15d21698f24d7796e20f6bc8815f9422\nironic:\n  db_password: RL6LqSDeb3eCWlJ2iTfL0l6o\n  enabled: false\n  swift_tempurl_key: yQ8wLkGKwmZ3TVZZul0IL6ca\n  user_password: XnNHZfQoK3ECDTkCeaRo56i3\nkernel_params:\n  kernel: console=tty0 net.ifnames=1 biosdevname=0 rootdelay=90 nomodeset\n  metadata:\n    group: general\n    label: Kernel parameters\n    weight: 60\nkeystone:\n  admin_token: wbbKYog35s0tBi0f9aiFlbvQ\n  db_password: jOkp5667FUNSH4XCbtUSOl7a\nlast_controller: node-4\nlibvirt_type: kvm\nmanagement_network_range: 192.168.0.0/24\nmaster_ip: 10.20.0.2\nmetadata:\n  label: Common\n  weight: 10\nmongo:\n  enabled: false\nmp:\n- point: '1'\n  weight: '1'\n- point: '2'\n  weight: '2'\nmurano:\n  db_password: P6tvepoN0mfniuQhxl7KQiHy\n  enabled: false\n  rabbit_password: Zk1IKuOinV83zz9YlLiJ0Yx5\n  user_password: Y8EL8pIzCvmpBq64bHn6lMoQ\nmurano-cfapi:\n  db_password: wv0gi7oOmcaf2Ckma4HLJX5L\n  enabled: false\n  rabbit_password: xK1uayOY6eWq9huAwJ3WEXeF\n  user_password: MKakPrUHJkQdmYuycpNIqRBS\nmurano_settings:\n  metadata:\n    group: openstack_services\n    label: Murano Settings\n    restrictions:\n    - action: hide\n      condition: settings:additional_components.murano.value == false\n      message: Murano is not enabled on the Additional Components section\n    weight: 20\n  murano_glance_artifacts_plugin: true\n  murano_repo_url: http://storage.apps.openstack.org/\nmysql:\n  root_password: dG9TwqNWB3y4iLUWWZGxBbKI\n  wsrep_password: cXpzUQ0IYjuDA44MFnlA4TM4\nnetwork_metadata:\n  nodes:\n    node-4:\n      fqdn: node-4.domain.tld\n      name: node-4\n      network_roles:\n        admin/pxe: 10.20.0.3\n        aodh/api: 192.168.0.3\n        ceilometer/api: 192.168.0.3\n        ceph/public: 192.168.1.1\n        ceph/radosgw: 192.168.36.152\n        ceph/replication: 192.168.1.1\n        cinder/api: 192.168.0.3\n        cinder/iscsi: 192.168.1.1\n        ex: 192.168.36.152\n        fw-admin: 10.20.0.3\n        glance/api: 192.168.0.3\n        glance/glare: 192.168.0.3\n        heat/api: 192.168.0.3\n        horizon: 192.168.0.3\n        ironic/api: 192.168.0.3\n        keystone/api: 192.168.0.3\n        management: 192.168.0.3\n        mgmt/corosync: 192.168.0.3\n        mgmt/database: 192.168.0.3\n        mgmt/memcache: 192.168.0.3\n        mgmt/messaging: 192.168.0.3\n        mgmt/vip: 192.168.0.3\n        mongo/db: 192.168.0.3\n        murano/api: 192.168.0.3\n        murano/cfapi: 192.168.0.3\n        neutron/api: 192.168.0.3\n        neutron/floating: null\n        neutron/private: null\n        nova/api: 192.168.0.3\n        nova/migration: 192.168.0.3\n        public/vip: 192.168.36.152\n        sahara/api: 192.168.0.3\n        storage: 192.168.1.1\n        swift/api: 192.168.0.3\n        swift/replication: 192.168.1.1\n      node_roles:\n      - primary-controller\n      - primary-database\n      - primary-keystone\n      - primary-neutron\n      - primary-rabbitmq\n      nova_cpu_pinning_enabled: false\n      nova_hugepages_enabled: false\n      swift_zone: '4'\n      uid: '4'\n      user_node_name: Untitled (ea:68)\n  vips:\n    management:\n      ipaddr: 192.168.0.2\n      is_user_defined: false\n      namespace: haproxy\n      network_role: mgmt/vip\n      node_roles:\n      - controller\n      - primary-controller\n      vendor_specific: null\n    public:\n      ipaddr: 192.168.36.151\n      is_user_defined: false\n      namespace: haproxy\n      network_role: public/vip\n      node_roles:\n      - controller\n      - primary-controller\n      vendor_specific: null\n    vrouter:\n      ipaddr: 192.168.0.1\n      is_user_defined: false\n      namespace: vrouter\n      network_role: mgmt/vip\n      node_roles:\n      - controller\n      - primary-controller\n      vendor_specific: null\n    vrouter_pub:\n      ipaddr: 192.168.36.150\n      is_user_defined: false\n      namespace: vrouter\n      network_role: public/vip\n      node_roles:\n      - controller\n      - primary-controller\n      vendor_specific:\n        iptables_rules:\n          ns_start:\n          - iptables -t nat -A POSTROUTING -o <%INT%> -j MASQUERADE\n          ns_stop:\n          - iptables -t nat -D POSTROUTING -o <%INT%> -j MASQUERADE\nneutron_advanced_configuration:\n  metadata:\n    group: network\n    label: Neutron Advanced Configuration\n    restrictions:\n    - action: hide\n      condition: cluster:net_provider != 'neutron'\n    weight: 20\n  neutron_dvr: false\n  neutron_l2_pop: false\n  neutron_l3_ha: false\n  neutron_qos: false\nnodes:\n- fqdn: node-4.domain.tld\n  internal_address: 192.168.0.3\n  internal_netmask: 255.255.255.0\n  name: node-4\n  public_address: 192.168.36.152\n  public_netmask: 255.255.255.0\n  role: primary-controller\n  storage_address: 192.168.1.1\n  storage_netmask: 255.255.255.0\n  swift_zone: '4'\n  uid: '4'\n  user_node_name: Untitled (ea:68)\n- fqdn: node-4.domain.tld\n  internal_address: 192.168.0.3\n  internal_netmask: 255.255.255.0\n  name: node-4\n  public_address: 192.168.36.152\n  public_netmask: 255.255.255.0\n  role: primary-database\n  storage_address: 192.168.1.1\n  storage_netmask: 255.255.255.0\n  swift_zone: '4'\n  uid: '4'\n  user_node_name: Untitled (ea:68)\n- fqdn: node-4.domain.tld\n  internal_address: 192.168.0.3\n  internal_netmask: 255.255.255.0\n  name: node-4\n  public_address: 192.168.36.152\n  public_netmask: 255.255.255.0\n  role: primary-keystone\n  storage_address: 192.168.1.1\n  storage_netmask: 255.255.255.0\n  swift_zone: '4'\n  uid: '4'\n  user_node_name: Untitled (ea:68)\n- fqdn: node-4.domain.tld\n  internal_address: 192.168.0.3\n  internal_netmask: 255.255.255.0\n  name: node-4\n  public_address: 192.168.36.152\n  public_netmask: 255.255.255.0\n  role: primary-neutron\n  storage_address: 192.168.1.1\n  storage_netmask: 255.255.255.0\n  swift_zone: '4'\n  uid: '4'\n  user_node_name: Untitled (ea:68)\n- fqdn: node-4.domain.tld\n  internal_address: 192.168.0.3\n  internal_netmask: 255.255.255.0\n  name: node-4\n  public_address: 192.168.36.152\n  public_netmask: 255.255.255.0\n  role: primary-rabbitmq\n  storage_address: 192.168.1.1\n  storage_netmask: 255.255.255.0\n  swift_zone: '4'\n  uid: '4'\n  user_node_name: Untitled (ea:68)\nnova:\n  db_password: 1notRv9WqAyTCsKIx4KoZ6Z7\n  state_path: /var/lib/nova\n  user_password: uiAW7tFP1TmUKwSc9rZn5UPh\nnova_quota: false\nopenstack_version: mitaka-9.0\noperator_user:\n  authkeys: ''\n  homedir: /home/fueladmin\n  metadata:\n    group: general\n    label: Operating System Access\n    weight: 15\n  name: fueladmin\n  password: 9q20j4PeelboytJ9z5kTcW8W\n  sudo: 'ALL=(ALL) NOPASSWD: ALL'\nplugins: []\npropagate_task_deploy: false\nprovision:\n  codename: trusty\n  engine:\n    master_ip: 10.20.0.2\n    password: 8hOBmOlABdB4DDuX5XXhI0Sl\n    url: http://10.20.0.2:80/cobbler_api\n    username: cobbler\n  image_data:\n    /:\n      container: gzip\n      format: ext4\n      uri: http://10.20.0.2:8080/targetimages/env_1_ubuntu_1404_amd64.img.gz\n    /boot:\n      container: gzip\n      format: ext2\n      uri: http://10.20.0.2:8080/targetimages/env_1_ubuntu_1404_amd64-boot.img.gz\n  metadata:\n    group: general\n    label: Provision\n    restrictions:\n    - action: hide\n      condition: 'false'\n    weight: 80\n  method: image\n  packages:\n  - acl\n  - anacron\n  - bash-completion\n  - bridge-utils\n  - bsdmainutils\n  - build-essential\n  - cloud-init\n  - curl\n  - daemonize\n  - debconf-utils\n  - gdisk\n  - grub-pc\n  - hpsa-dkms\n  - hwloc\n  - i40e-dkms\n  - linux-firmware\n  - linux-firmware-nonfree\n  - linux-headers-generic-lts-trusty\n  - linux-image-generic-lts-trusty\n  - lvm2\n  - mcollective\n  - mdadm\n  - multipath-tools\n  - multipath-tools-boot\n  - nailgun-agent\n  - nailgun-mcagents\n  - network-checker\n  - ntp\n  - openssh-client\n  - openssh-server\n  - puppet\n  - python-amqp\n  - ruby-augeas\n  - ruby-ipaddress\n  - ruby-json\n  - ruby-netaddr\n  - ruby-openstack\n  - ruby-shadow\n  - ruby-stomp\n  - systemd-shim\n  - telnet\n  - ubuntu-minimal\n  - ubuntu-standard\n  - uuid-runtime\n  - vim\n  - virt-what\n  - vlan\n  - xcloud-init\npublic_network_assignment:\n  assign_to_all_nodes: false\n  metadata:\n    group: network\n    label: Public network assignment\n    restrictions:\n    - action: hide\n      condition: cluster:net_provider != 'neutron'\n    weight: 10\npublic_ssl:\n  cert_data: ''\n  cert_source: self_signed\n  horizon: false\n  hostname: public.fuel.local\n  metadata:\n    group: security\n    label: Public TLS\n    weight: 110\n  services: false\npuppet:\n  manifests: rsync://10.20.0.2:/puppet/mitaka-9.0/manifests/\n  modules: rsync://10.20.0.2:/puppet/mitaka-9.0/modules/\npuppet_debug: true\nquantum: true\nquantum_settings:\n  L2:\n    base_mac: fa:16:3e:00:00:00\n    phys_nets:\n      physnet1:\n        bridge: br-floating\n        vlan_range: null\n      physnet2:\n        bridge: br-prv\n        vlan_range: 1000:1030\n    segmentation_type: vlan\n  L3:\n    use_namespaces: true\n  database:\n    passwd: tUdZnWImSt0BKUSeMRJB05os\n  default_floating_net: admin_floating_net\n  default_private_net: admin_internal_net\n  keystone:\n    admin_password: NZy11l1QLWs6QXtFMNpHpzMZ\n  metadata:\n    metadata_proxy_shared_secret: BBe6zzRryHjhrxwZKgTFgMW1\n  predefined_networks:\n    admin_floating_net:\n      L2:\n        network_type: flat\n        physnet: physnet1\n        router_ext: true\n        segment_id: null\n      L3:\n        enable_dhcp: false\n        floating:\n        - 192.168.36.190:192.168.36.200\n        gateway: 192.168.36.254\n        nameservers: []\n        subnet: 192.168.36.0/24\n      shared: false\n      tenant: admin\n    admin_internal_net:\n      L2:\n        network_type: vlan\n        physnet: physnet2\n        router_ext: false\n        segment_id: null\n      L3:\n        enable_dhcp: true\n        floating: null\n        gateway: 192.168.111.1\n        nameservers:\n        - 8.8.4.4\n        - 8.8.8.8\n        subnet: 192.168.111.0/24\n      shared: false\n      tenant: admin\nrabbit:\n  password: C0xPfRUuDI6Zx7xICwth8dkW\nrelease:\n  name: Mitaka on Ubuntu 14.04\n  operating_system: Ubuntu\n  version: mitaka-9.0\nrepo_setup:\n  installer_initrd:\n    local: /var/www/nailgun/ubuntu/x86_64/images/initrd.gz\n    remote_relative: dists/trusty/main/installer-amd64/current/images/netboot/ubuntu-installer/amd64/initrd.gz\n  installer_kernel:\n    local: /var/www/nailgun/ubuntu/x86_64/images/linux\n    remote_relative: dists/trusty/main/installer-amd64/current/images/netboot/ubuntu-installer/amd64/linux\n  metadata:\n    always_editable: true\n    group: general\n    label: Repositories\n    weight: 50\n  repos:\n  - name: ubuntu\n    priority: null\n    section: main universe multiverse\n    suite: trusty\n    type: deb\n    uri: http://archive.ubuntu.com/ubuntu/\n  - name: ubuntu-updates\n    priority: null\n    section: main universe multiverse\n    suite: trusty-updates\n    type: deb\n    uri: http://archive.ubuntu.com/ubuntu/\n  - name: ubuntu-security\n    priority: null\n    section: main universe multiverse\n    suite: trusty-security\n    type: deb\n    uri: http://archive.ubuntu.com/ubuntu/\n  - name: mos\n    priority: 1050\n    section: main restricted\n    suite: mos9.0\n    type: deb\n    uri: http://10.20.0.2:8080/mitaka-9.0/ubuntu/x86_64\n  - name: mos-updates\n    priority: 1050\n    section: main restricted\n    suite: mos9.0-updates\n    type: deb\n    uri: http://mirror.fuel-infra.org/mos-repos/ubuntu/9.0/\n  - name: mos-security\n    priority: 1050\n    section: main restricted\n    suite: mos9.0-security\n    type: deb\n    uri: http://mirror.fuel-infra.org/mos-repos/ubuntu/9.0/\n  - name: mos-holdback\n    priority: 1100\n    section: main restricted\n    suite: mos9.0-holdback\n    type: deb\n    uri: http://mirror.fuel-infra.org/mos-repos/ubuntu/9.0/\n  - name: Auxiliary\n    priority: 1150\n    section: main restricted\n    suite: auxiliary\n    type: deb\n    uri: http://10.20.0.2:8080/mitaka-9.0/ubuntu/auxiliary\nresume_guests_state_on_host_boot: true\nroles:\n- master\nrun_ping_checker: true\nsahara:\n  db_password: vhJ5wvhJBPwnIFMJBBkLtAc8\n  enabled: false\n  user_password: p2eoH89EjeUAA2IY8kUqLEoV\nsecurity_groups: iptables_hybrid\nservice_user:\n  homedir: /var/lib/fuel\n  metadata:\n    group: general\n    label: Service user account\n    restrictions:\n    - action: hide\n      condition: 'true'\n    weight: 10\n  name: fuel\n  password: hDEwC5vK3FAM2PjxqrdJ5Kb0\n  root_password: r00tme\n  sudo: 'ALL=(ALL) NOPASSWD: ALL'\nstorage:\n  admin_key: AQA+uAJZAAAAABAAbp0qUtuS/8sInG2CW5OGzg==\n  auth_s3_keystone_ceph: false\n  bootstrap_osd_key: AQA+uAJZAAAAABAAmUf1D3TPPYMKTpMbb3HsQA==\n  ephemeral_ceph: false\n  fsid: de123aba-9956-45ae-ad2e-bae734c39927\n  images_ceph: false\n  images_vcenter: false\n  metadata:\n    group: storage\n    label: Storage Backends\n    weight: 60\n  mon_key: AQA+uAJZAAAAABAApt7MhcuRbVRypFOk/Xmu2g==\n  objects_ceph: false\n  osd_pool_size: '3'\n  per_pool_pg_nums:\n    .rgw: 128\n    backups: 128\n    compute: 128\n    default_pg_num: 128\n    images: 128\n    volumes: 128\n  pg_num: 128\n  radosgw_key: AQA+uAJZAAAAABAASYiav0Eyt0sgTsxqPppi5g==\n  volumes_block_device: false\n  volumes_ceph: false\n  volumes_lvm: true\nstorage_network_range: 192.168.1.0/24\nswift:\n  user_password: Ox5NysYCAB6jBAjmiLrflpiB\nsyslog:\n  metadata:\n    enabled: false\n    group: logging\n    label: Syslog\n    toggleable: true\n    weight: 50\n  syslog_port: '514'\n  syslog_server: ''\n  syslog_transport: tcp\ntask_deploy: true\nuid: master\nuse_cow_images: true\nuse_vcenter: false\nworkloads_collector:\n  create_user: false\n  enabled: true\n  metadata:\n    group: general\n    label: Workloads Collector User\n    restrictions:\n    - action: hide\n      condition: 'true'\n    weight: 10\n  password: 3Ee7uZ7MuS5yhDmDvkjh1Zh8\n  tenant: services\n  username: fuel_stats_user\n",
                            "cwd": "/",
                            "permissions": "0640"
                        },
                        "fail_on_error": true,
                        "required_for": [
                            {
                                "node_id": null,
                                "name": "pre_deployment_start"
                            }
                        ],
                        "type": "upload_file",
                        "id": "upload_configuration"
                    }
                ]
            },
            "noop_run": false
        },
        "respond_to": "deploy_resp",
        "method": "task_deploy",
        "api_version": "1"
    }
]