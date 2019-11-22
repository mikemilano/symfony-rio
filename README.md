# Symfony 4 on Rio Demo

This is an example on how to package the symfony demo application into a Docker image.

This was [adapted](https://github.com/bashofmann/symfony-demo-kubernetes) and prepared to 
run on [Rio](https://github.com/rancher/rio).

Symfony Demo Application
========================

The "Symfony Demo Application" is a reference application created to show how
to develop Symfony applications following the recommended best practices.

Usage
-----

There's no need to configure anything to run the application. Just execute this
command to run the built-in web server and access the application in your
browser at <http://localhost:8000>:

```bash
$ cd symfony-demo/
$ php bin/console server:run
```

Alternatively, you can [configure a fully-featured web server][2] like Nginx
or Apache to run the application.

Run in Kubernetes
-----------------

```bash
$ docker build -t mikemilano/symfony-rio:1.0.0 .
$ kubectl create -f deployment
```

Tests
-----

Execute this command to run tests:

```bash
$ cd symfony-demo/
$ ./vendor/bin/simple-phpunit
