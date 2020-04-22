# Node Packer

## Pre-requisites

- Chef
- Packer
- Git

## Packer

Packer is an open source tool used to create identical machine images from a single source configuration. Using a JSON file we can configure our packer.json to set up images. We have used Chef to configure our provisions, which the packer.json will use to install onto our image. After creating our image, we can use them to create EC2's already provisioned.

## How to run

To clone this repo:
```
$ git clone git@github.com:hovell722/NodePacker.git
```

You may have to edit lines 10, 12 and 13 in `packer.json` to your own AWS subnet id and your own SSH key names which you are using.

To pull cookbooks needed from github run:

```
$ berks vendor
```

A berks-cookbooks folder should then be created.

To create the AMI:

```
$ packer validate packer.json

$ packer build packer.json
```
