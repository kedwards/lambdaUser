# lambdaUser

GOOS=linux GOARCH=amd64 CGO_ENABLED=0 go build -o build/main cmd/main.go

# Endpoint 
endpoint=https://7706q5iygf.execute-api.us-west-2.amazonaws.com/staging

# Add user
curl --header "Content-Type: application/json" --request POST --data '{"email": "kedwards@kevinedwards.ca", "firstName": "Kevin", "lastName": "Edwards"}' $endpoint

# List users
curl -X GET $endpoint

# List user by email
curl -X GET $endpoint\?email\=kedwards@kevinedwards.ca

# Update user
curl --header "Content-Type: application/json" --request PUT --data '{"email": "kedwards@kevinedwards.ca", "firstName": "Kevin Great", "lastName": "Edwards"}' $endpoint

# Delete user
curl -X DELETE $endpoint\?email\=kedwards@kevinedwards.ca
