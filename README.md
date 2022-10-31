# TrustChain

Ethereum Mainnet Smart Contract Address: 0x25c3950BeBA4a779C29C54A9E55B44B716B8826F

Smart contract is executed once a day with the following data:
   - `version` - data format version (currently 0 - for demo data, 1 - first production data)
   - `dateFrom` - timestamp of the first record date
   - `dateTo` - timestamp of the last record date
   - `hash` - sha256 hash of the data

Example transaction on Etherscan is [here](https://etherscan.io/tx/0x224d0ff03ad96841d82bc42f2cf9497a6715c15098b8ca8275f2552359d238e8)


In the above example we can decode information in the following way
- `version=0` it means this is demo transaction
- `dateFrom=1664643553348` can be converted to: 1 October 2022 16:59:13.348 UTC
- `dateTo=1664693505555` can be converted to: 2 October 2022 06:51:45.555 UTC
- `hash=ba3032b4fa930c12891df70dd8039031822ae327b8fee6e725b271d51271ce64` 

Hash is a result of applying cryptographics sha256 function on following data:
```json
[{"key":"F0dBFEIUQREOGxRHEQ4XQBMVDhobERoOQhIaFBMaFRZFGxQU","publicKey":"0xceab0657d0197a3cad4a75ee4ed714908d00fd4b","hash":"028f9f7fef9827f0b3f5c26e08939df095ad70217d45e04f928fc8a86eeef87b"},{"key":"QhEbRUZCERcORhsaEA4XQRRGDkIVQREORUZBFkUUFRRGRRoV","publicKey":"0xc3ecb9dfb53d535d15bd1f6a3e39cc1a5e0dd7a5","hash":"056dae2f349d3aefc233927c8c630ba6b5c8b83f873bc137ac62615d93c5fc19"},{"key":"QhIbFEJFRRYORhpAFw4XRRAWDhtGFEEOGxBFEhoWF0cRGhVB","publicKey":"0x903eae5eb4fd5bdd4bbec49f747244462e8d1dae","hash":"474d6218a9042528ce9b9d99cd8e4a5fafed60552dfc4567e546b868b2412147"},{"key":"EEVAE0YRRhcOQkEWQA4XQhUaDkIaQkYOQEcRRUdFEEEVRkJF","publicKey":"0xf4b909147d269c1c28d3fc74aa1b8bf832c72799","hash":"99f7693feaf31437ea2837e66eef8fb0cca74fa8f46907ecaab56ae463e28306"},{"key":"GxYbQhcaExQOR0YVQg4XFhYRDkISFkAORxtFExVCRxdBRkYT","publicKey":"0x566a2dff5ca6df28572893672dc1525baff1d10e","hash":"32645da9fe7d5d628b5618a58de4dd4668c9dc708005780119df36ff6dc7ed79"}]
```
Where:
- `key` - is the encrypted userId
- `publicKey` - is the user Ethereum wallet address for the TrustChain, if he/she provided this data in Exfluency portal, null means we don’t have his address (in this sample is demo data only)
- `hash` - sha256 function applied on user TrustChain records

For example user: `F0dBFEIUQREOGxRHEQ4XQBMVDhobERoOQhIaFBMaFRZFGxQU` we have sha256 hash: `028f9f7fef9827f0b3f5c26e08939df095ad70217d45e04f928fc8a86eeef87b` applied on following data:

```json
[{"ratedAssignmentId":"RRNAFBYbG0EOFREaFg4XExIaDkIWGkAOFhpHFUUUGhIQEkcW","ratingAssignmentId":"GhVFR0dCEEUOQkdHFw4XFUUTDhsSFhoOFBFGEBIREUYbEBoS","ratedExecutorId":"F0dBFEIUQREOGxRHEQ4XQBMVDhobERoOQhIaFBMaFRZFGxQU","ratingExecutorId":"QhRHFxVAEkUOQkYaFg4XGxITDhoQEUUOGkEWFhYVFBMQFxNC","entryDate":"2022-10-01T16:59:13.348Z","languageFrom":"it_it","languageTo":"en_us","assignmentScore":7.927038669586182,"assetCount":233,"recycledAssetCount":211,"deadlineMet":false,"taxonomyKey":"Life sciences"},{"ratedAssignmentId":"GxMaEhMTRUIOGhZHQA4XEBZGDhoQG0IOFkcbExIbFBZAEBES","ratingAssignmentId":"RhETFhRFEUAOERAVQA4XGxAUDhsUFEYOERAXEkEURRMVQEcQ","ratedExecutorId":"F0dBFEIUQREOGxRHEQ4XQBMVDhobERoOQhIaFBMaFRZFGxQU","ratingExecutorId":"QhRHFxVAEkUOQkYaFg4XGxITDhoQEUUOGkEWFhYVFBMQFxNC","entryDate":"2022-10-02T06:51:45.555Z","languageFrom":"it_it","languageTo":"en_us","assignmentScore":8.411765098571777,"assetCount":51,"recycledAssetCount":39,"deadlineMet":false,"taxonomyKey":"Life sciences"}]
```

Formatted:
```json
[
   {
      "ratedAssignmentId":"RRNAFBYbG0EOFREaFg4XExIaDkIWGkAOFhpHFUUUGhIQEkcW",
      "ratingAssignmentId":"GhVFR0dCEEUOQkdHFw4XFUUTDhsSFhoOFBFGEBIREUYbEBoS",
      "ratedExecutorId":"F0dBFEIUQREOGxRHEQ4XQBMVDhobERoOQhIaFBMaFRZFGxQU",
      "ratingExecutorId":"QhRHFxVAEkUOQkYaFg4XGxITDhoQEUUOGkEWFhYVFBMQFxNC",
      "entryDate":"2022-10-01T16:59:13.348Z",
      "languageFrom":"it_it",
      "languageTo":"en_us",
      "assignmentScore":7.927038669586182,
      "assetCount":233,
      "recycledAssetCount":211,
      "deadlineMet":false,
      "taxonomyKey":"Life sciences"
   },
   {
      "ratedAssignmentId":"GxMaEhMTRUIOGhZHQA4XEBZGDhoQG0IOFkcbExIbFBZAEBES",
      "ratingAssignmentId":"RhETFhRFEUAOERAVQA4XGxAUDhsUFEYOERAXEkEURRMVQEcQ",
      "ratedExecutorId":"F0dBFEIUQREOGxRHEQ4XQBMVDhobERoOQhIaFBMaFRZFGxQU",
      "ratingExecutorId":"QhRHFxVAEkUOQkYaFg4XGxITDhoQEUUOGkEWFhYVFBMQFxNC",
      "entryDate":"2022-10-02T06:51:45.555Z",
      "languageFrom":"it_it",
      "languageTo":"en_us",
      "assignmentScore":8.411765098571777,
      "assetCount":51,
      "recycledAssetCount":39,
      "deadlineMet":false,
      "taxonomyKey":"Life sciences"
   }
]
```

Where:
- `ratedExecutorId` - is encrypted userid which recived score from the Trust Miner identified by ratingExecutorId
- `ratedAssignmentId` - encrypted assignemnt id of the project which user worked on
- `ratingAssignmentId` - encrypted assignement id of the project which Trust Miner worked on
- `entryDate` - assignement delivery date
- `languageFrom, languageTo, taxonomyKey` - are the translation project parameters
- `assignmentScore` - is the Exfluency score
- `assetCount` - number of assets (translation pairs) in the project
- `recycledAssetCount` - number of recycled assets
- `deadlineMet` - project delivered on time
