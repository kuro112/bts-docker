# bts-docker

```!#/bin/bash

echo "###################"
echo ""
echo "BTS Docker Image 1.2 By Kuro"
echo ""
echo "./fr - First Run Script"
echo "./btsu - Update Script"
echo "./btsr - Reload Script"
echo ""
echo "located within /
echo ""
echo "Data Volume mounting as btsdata to /bitshares"
echo ""
echo "###################"

docker create -v /bitshares --name btsdata ubuntu;
docker run -tid -p 8092:8092 --name bitshares -volumes-from btsdata kuro112/bitshares:bitshares2;
echo "Bitshares RPC Installing";
docker exec -ti bitshares "./fr";
echo "Bitshares RPC Running on Port 0.0.0.0:8092"

echo "###################"
echo ""
echo "To access: 
docker attach bitshares (hit enter)"
echo ""
echo "Once inside:
screen -x wallet"
echo "From here you may import your keys"
echo ""
echo "To Detach: 
hit CTRL + p then CTRL + q"
echo ""
echo "To update: 
docker exec -it bitshares ./btsu"
echo ""
echo "###################"
```
