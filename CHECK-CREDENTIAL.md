# Check a verifiable credential

```
curl --request POST \
    'http://ensuresec.solutions.iota.org/api/v1/verification/check-credential?api-key=94F5BA49-12B6-4E45-A487-BF91C442276D' \
    -H "Content-Type: application/json" \
    --data-binary "@./integration-services/clients/summer-school-client/src/create-credentials/ExamRatingCredential.json" | jq .
```