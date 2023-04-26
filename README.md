# urlShorty
A URL shortening microservice written in Go.

# How to run the application
- `go run main.go`
You should see the message "Starting server on port 8080".

Go to:
This will serve the Swagger UI at http://localhost:8080/swagger/index.html. You can customize the path and configuration by modifying this line.

# Test request payload
- 
- 
`
    {
        "target_url": "https://www.google.com"
    }
`
The response should be like:
`
{
    "short_url": "http://localhost:8080/aBcDeFg"
}
`

Test the shortened URL by visiting http://localhost:8080/aBcDeFg in your browser. You should be redirected to the original URL.

Setting up Linode and GitHub Actions
Create a new Linode API key by going to your account settings and clicking on "API Tokens". Generate a new token with read/write permissions.

Create a new Linode instance by going to the Linode dashboard and clicking on "Create an Instance". Choose a plan and data center region that suits your needs.

SSH into your Linode instance:

ssh root@<your-linode-ip-address>

Install MongoDB on Linode

sudo apt update
sudo apt install mongodb


Enable and start MongoDB
sudo systemctl enable mongodb
sudo systemctl start mongodb

Add a new GitHub Actions workflow by creating a file .github/workflows/deploy.yml with the following contents:

# If missing swag, follow this command:
- go install github.com/swaggo/swag/cmd/swag@latest