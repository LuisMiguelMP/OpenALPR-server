# OpenALPR-server
NodeJS server for OpenALPR to recognize vehicle license plates from image.

# Running
docker run -p 8080:8080 samuelbr/openalpr-server

# Making a request
curl -X GET http://localhost:8080/?image_url=http://www.example.com/yourimage.jpg&type=eu

curl -X POST --data-binary "@yourimage.jpg" http://localhost:8080/?country_code=gb

# Google Cloud Commands to build with Cloud Run
gcloud builds submit --tag gcr.io/<GOOGLE_CLOUD_PROJECT_ID>/openalpr .

gcloud beta run deploy openalpr --image gcr.io/<GOOGLE_CLOUD_PROJECT_ID>/openalpr --region australia-southeast1 --platform managed --allow-unauthenticated --quiet
