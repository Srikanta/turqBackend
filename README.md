# Build
`docker build -t turq:dev .`
# Run
`docker run -d -e jwt_secret="$jwt_secret" -e postgres_pass="$postgres_pass" -e postgres_url="$postgres_url" -e postgres_user="$postgres_user" -e stripe_key="$stripe_key" -p 8080:8080 turq:dev`

# Push to AWS
`aws ecr get-login-password --region us-east-2 | docker login --username AWS --password-stdin 503410576865.dkr.ecr.us-east-2.amazonaws.com`

`docker build -t turq .`

`docker tag turq:latest 503410576865.dkr.ecr.us-east-2.amazonaws.com/turq:latest`

`docker push 503410576865.dkr.ecr.us-east-2.amazonaws.com/turq:latest`