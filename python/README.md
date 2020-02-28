export PORT=$(cat default-env.json | jq -r '.PORT') ; export VCAP_SERVICES=$(cat default-env.json | jq -r '.VCAP_SERVICES')

python3 server.py

python3 -m ptvsd --host localhost --port 5678 server.py
