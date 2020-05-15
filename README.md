# packer-february-2020

    This documentation covers:  
What is Packer? 
Installation of Packer 

    What is Packer? 
Packer is an open source tool for creating identical machine images for multiple platforms from a single source configuration. Packer is lightweight, runs on every major operating system, and is highly performant, creating machine images for multiple platforms in parallel. Packer does not replace configuration management like Chef or Puppet. In fact, when building images, Packer is able to use tools like Chef or Puppet to install software onto the image. 

    Installation of Packer 
wget https://releases.hashicorp.com/packer/1.5.1/packer_1.5.1_linux_amd64.zip 
unzip packer_1.5.1_linux_amd64.zip 
sudo mv /sbin/packer        /tmp                                                 #By default centos comes with a tool called "packer". In order to avoid issues we have to move default packer to /tmp 
sudo mv packer /bin 
packer version 

 

    See available commands 
root@ip-172-31-45-232 tools]# packer 
Usage: packer [--version] [--help] <command> [<args>] 
Available commands are: 
    fix             fixes templates from old versions of packer 
    build           build image(s) from template 
    console         creates a console for testing variable interpolation 
    inspect         see components of a template 
    validate        check that a template is valid 
    version         Prints the Packer version 


    comment in Packer file
By default json file does not take a comment like a yaml file. Json file is intended to be used by machines while yaml is user oriented. However, packer offers a comment option within a file  

    Comments 
JSON doesn't support comments and Packer reports unknown keys as validation errors. If you'd like to comment your template, you can prefix a root level key with an underscore. Example: 
{ 
  "_comment": "This is a comment", 
  "builders": [ 
    {} 
  ] 
} 
 
Important: Only root level keys can be underscore prefixed. Keys within builders, provisioners, etc. will still result in validation errors. 


    This is the nice part of thing...

     {
        "type": "breakpoint",
        "note": "Wait for you to delete"
        }
    ]

    so it will ask you to delete or not. Press enter it deletes for you

    ##once you build artemis_python.json go to the security group and allow: "all tcp" then get ip, put browser and add port :5000 and you will see artemis

 
This is not all explanation or guide about installation of Packer. But codes will be enough to build your Packer. 
    This will be the full documentations about Packer if you can reach it:
https://onedrive.live.com/redir?resid=34D15D0E43186458%21144&page=View&wd=target%28Packer%20Basics.one%7C9ed07d12-ae8a-ed41-87cc-aa786c67f0cc%2FBasic%20Steps%20in%20packer%7C9433735c-60dd-5948-9a64-dbe6db9ead8a%2F%29 