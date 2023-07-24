<script lang="ts">

    const isConnected = await Fuel.connect();
    console.log("Connection response", isConnected)

async (connectorName: string) => {
  console.log(`Select connector "${connectorName}"!`);
  await fuel.selectConnector(connectorName);
  console.log(`Connector "${connectorName}" connected`);

  if(Fuel.connect() === isConnected) {
    await Fuel.disconnect()
  }
};

</script>