# Remember to setup NEW_RELIC_LICENSE_KEY env. var first:
# This one is for Disney workshop

export NEW_RELIC_LICENSE_KEY=e6d9262e1d82bcf0cd5a5926b32f39d480cab60a

# Start the little demo app
./disney-simba

# This is a Hey loadtesting command that will run some load against the app.
hey -n 10000 -c 1 -q 2 http://localhost:8000/set_name &  hey -n 10000 -c 1 -q 2 http://localhost:8000/segments &  hey -n 10000 -c 1 -q 2 http://localhost:8000/ &  hey -n 10000 -c 1 -q 2 http://localhost:8000/mysql &  hey -n 10000 -c 1 -q 2 http://localhost:8000/external