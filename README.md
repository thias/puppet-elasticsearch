# puppet-elasticsearch

## Overview

Install, enable and configure Elasticsearch.

* `elasticsearch` : Main class to install and enable the server

## Example Usage

Simple instance with the default configuration :

    include elasticsearch

Instance with a few tweaks :

    class { 'elasticsearch':
      network_bind_host      => '192.168.0.1',
      transport_tcp_compress => 'true',
    }

Instance with even more options, with no existing matching module parameters :

    class { 'elasticsearch':
      elasticsearch_options => {
        'index.refresh_interval'             => '10s',
        'index.term_index_interval'          => '512',
        'index.translog.flush_threshold_ops' => '50000',
        'indices.memory.index_buffer_size'   => '20%',
      },
    }

