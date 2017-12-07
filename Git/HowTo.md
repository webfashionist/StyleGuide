# HowTo Git

## Generate SSH keys

If you want to use `git` through a SSH connection, you'll need a public and private key first.
Here's how you can generate them:

```Shell
$ ssh-keygen -t rsa -b 4096 -C "<your_email_address>"
```

This will now generate the public/private RSA key pair, 
then you will be prompted to "Enter a file in which to save the key".
After that, you will get a second prompt which asks you to type a secure passphrase. This passphrase will be required at every SSH connection.

Now, the SSH key needs to be added to the authentication agent:

```Shell
$ eval `ssh-agent`
$ ssh-add ~/.ssh/id_rsa
```

Change the `ssh-add` path accordingly if you chose your own SSH directory.

After this, you will need to add your new SSH public key (`id_rsa.pub`) to your account (e.g. Github or Bitbucket).

## SSH port: connection refused

Depending on your router, or if you are using a public WIFI spot, it could be that the default SSH port is blocked.

To change the SSH port for your machine, open the SSH configuration file using `vim` or any other tool:

```Shell
$ vim ~/.ssh/config
```

The above path may of course change, if you chose another path for your SSH configurations.
You can now add the configurations for Github, Bitbucket or any other host:

```Text
Host github.com
  Hostname ssh.github.com
  Port 443
```

```Text
Host bitbucket.org
  Hostname  altssh.bitbucket.org
  Port  443
```


## SSH public key issues

If you already have a public key somewhere on your machine, you sometimes need to add it to your authentication agent in order to be able to connect to your remote repository.

```Shell
$ eval `ssh-agent`
$ ssh-add ~/.ssh/id_rsa
```

Change the `ssh-add` path accordingly if you chose your own SSH directory.


## Submodules

### Add a submodule

Adding submodules to your repository can be very useful, as you don't need to update them manually by downloading and copying the files to the right place.

Here's how you can add a separate git repository to your existing repository:

```Shell
$ git submodule add <URL_to_submodule> <local_path_to_place_submodule>
```


### Update/init submodule

Normally, `git pull` inside the repository won't update the submodules inside it. There's a specific `git` command which helps you out here:

```Shell
$ git submodule update --init --recursive
```