# API

The Strike API input and output formats are specified by [Protocol Buffers](https://developers.google.com/protocol-buffers/), known colloquially as protobufs. Unlike typical protobufs endpoints, the Strike endpoints support JSON for input and output in addition to the protobufs binary format. To use JSON in both the input and the output, specify the headers "`Content-Type: application/json`" and "`Accept: application/json`" in the request.

API keys are currently optional, and are included in the HTTP header `strike-api-key;` you can request keys from Strike in the \#development channel of our [Discord](https://discord.gg/874ntdw) server. In the future, API keys will be required to access the API.

