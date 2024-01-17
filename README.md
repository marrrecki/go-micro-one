https://go.dev/doc/tutorial/web-service-gin

# Get single
curl http://localhost:8080/albums/2

# Get all
curl http://localhost:8080/albums \
    --header "Content-Type: application/json" \
    --request "GET"

# Create new
curl http://localhost:8080/albums \
    --include \
    --header "Content-Type: application/json" \
    --request "POST" \
    --data '{"id": "4","title": "The Modern Sound of Betty Carter","artist": "Betty Carter","price": 49.99}'