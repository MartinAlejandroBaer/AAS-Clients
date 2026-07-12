## Basic Http AAS Client Updater

This is a basic application using Crystal and mainly the HTTP standar Library in order to connect with an AAS Server deployed following the Specifications of the AAS Part 2.

This script was generated just for a proof of concept and testing the available AAS Servers tools.

Code

```crystal
require "http/client"
require "json"
require "time"
require "base64"

serverIpAddress = "localhost"
port = 1008

submodelId = "https://example.com/ids/sm/3264_2292_6062_3308"
base64SubmodelId = Base64.strict_encode(submodelId)
puts "Generated Base64Id: #{base64SubmodelId}" # Check the generated Base64 Id in the console

submodelElementIdShort = "DetectionCounter"
route = "http://#{serverIpAddress}:#{port}/api/v3.0/submodels/#{base64SubmodelId}/submodel-elements/#{submodelElementIdShort}/$value"

puts "Generated Route: #{route}" # Check the generated route

while true
    randomInt = Random.new.rand(100) # Generation of a random number to update the property
    createBody = {"DetectionCounter" => randomInt}
    puts "[#{Time.local(location: Time::Location.load("Europe/Berlin"))}] Sent value #{createBody.to_json}" # Create a log event to check the updated value
    # PATCH to REST API Command to update a submodel element property
    response = HTTP::Client.patch(route, headers: HTTP::Headers{"User-Agent" => "From Crystal"}, body: createBody.to_json )
    sleep 2.seconds # We introduce a delay of 2 seconds to update the new value
end
```

The code can be executed using the following command:
```bash
crystal run httpClient.cr
```

Version of Crystal
* Crystal 1.20.3 [2f93147c0] (2026-07-02)
* LLVM: 20.1.8
* Default target: x86_64-unknown-linux-gnu


