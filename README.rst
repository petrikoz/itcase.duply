************
ItCase.Duply
************

`Ansible`_ role for setup backups with `duply <http://duply.net/>`_.

Usage
=====

.. code-block:: yaml

  - hosts: all
    sudo: true

    roles:
    - itcase.duply

    vars:
      s3_access_key: S3-ACCESS-KEY
      s3_secret_key: S3-SECRET-KEY
      s3_bucket: S3-BUCKET-NAME
      s3_host: S3-STORAGE-HOST-NAME

      duply_name: DUPLY-CONFIG-NAME
      duply_includes: [
        'path to included catalog or file',
        'another path to included catalog or file'
      ]
      duply_excludes: [
          'path to excluded catalog or file',
          'another path to excluded catalog or file'
      ]
      duply_log: 'path to log file for duply cron run'

Variables
=========

.. code-block:: yaml

  s3_access_key: S3-ACCESS-KEY                      # Access key for S3 storage
  s3_secret_key: S3-SECRET-KEY                      # Secret key for S3 storage
  s3_bucket: S3-BUCKET-NAME                         # Bucket name in S3 storage
  s3_host: S3-STORAGE-HOST-NAME                     # Host name of S3 storage

  s3cmd_enable: true                                # Enable install and configure s3cmd
  s3cmd_extras: [                                   #
    'multipart_chunk_size_mb = 5',                  # Extra params for s3cfg
    'signature_v2 = True'                           #
  ]

  duply_enable: true                                # Enable install and configure duply
  duply_name: DUPLY-CONFIG-NAME                     # Duply's profile name

  duply_includes: [                                 # List of pathes which will
    'path to included catalog or file',             # add as includes in
    'another path to included catalog or file'      # /root/.duply/{{ duply_name }}/excludes
  ]
  duply_excludes: [                                 # List of pathes which will
    'path to excluded catalog or file',             # add as excludes in
    'another path to excluded catalog or file',     # /root/.duply/{{ duply_name }}/excludes
  ]
  duply_log: 'path to log file for duply cron run'  # In this file write duply's cron logs
  duply_run: true                                   # Enable first run

  boto_enable: true                                 # Enable install and configure boto

License
=======

Licensed under the Apache License, Version 2.0. See the LICENSE file for details.


.. _Ansible: https://github.com/ansible/ansible
