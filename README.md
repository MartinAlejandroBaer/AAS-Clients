# Basics AAS Clients
In this repository, basic scripts for interaction with AAS Servers are going to be defined. All of these scripts are just generated for a proof of concept of the different alternatives for data and information consumption and for testing the available AAS Servers tools. 

The idea of this repo is to collect different alternatives for data and information consumption from different AAS Servers using different programming languages and I4.0-Compliant Communication procotols, such as: AMQP, HTTP, MQTT and OPC UA

## Implementation Schema
<p align="center">
  <img src="schema.svg" width="200px"/>
</p>

The idea is to connect the clients to an AAS Servers using the protocols that they offer. The final goal is to connect such clients to a low-level interface that will allowing real-time data acquisition. In this, case the clients can be programmed in such a way that industrial low-level interfaces can be connected.

### CrystalClient - HTTP
* Link to the script => [Link](https://github.com/MartinAlejandroBaer/httpAASupdater/tree/main/CrystalClient)
* In this case, a simple http client using the Crystal programming language and its standar HTTP library. Other libraries such as "json", "time" and "base64" are also utilised. 
* The http client in this case connects with a standar HTTP Server created following the specifications "Specification of the Asset Administration Shell Part 2: Application Programming Interfaces – IDTA Number: 01002" (See [Link](https://industrialdigitaltwin.io/aas-specifications/IDTA-01002/v3.1.3/index.html))
* For the deploymenf ot the AAS, the tool "FA³ST Service" was testet (See [Link](https://faaast-service.readthedocs.io/en/latest/))

### Impotant Notes!
The idea is simply to contribute to the state of the art in integrating AASs Type II with real-time infrastructures.

These are projects I generally work on in my spare time, since this isn't my main occupation. That is why I hope to contribute and that these ideas will be useful in some way—not only from a conceptual standpoint, but also in practice.
