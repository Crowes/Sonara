<template>
    <li>
        <a>
            <i class="material-icons left">{{connectionIcon}}</i>
            {{connectionStatus}} to {{deviceName}}
        </a>
    </li>
</template>

<script>
    const { log } = require('../../javascript/utils');

    module.exports = {
      props: {connectionStatus: String, deviceName: String},
      mounted: () => log('ConnectionIcon', 'Mounted'),
      computed: {
        connectionIcon: function () {
          switch (this.connectionStatus) {
            case 'Connected': return 'signal_cellular_4_bar';
            case 'Struggling to Connect': return 'signal_cellular_connected_no_internet_4_bar';
            default: return 'signal_cellular_null';
          }
        }
      }
    }
</script>

