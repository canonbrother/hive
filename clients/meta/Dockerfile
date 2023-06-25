# Docker container spec for building the master branch of go-ethereum.
#
# The build process it potentially longer running but every effort was made to
# produce a very minimalistic container that can be reused many times without
# needing to constantly rebuild.

ARG branch=HEAD-6740cee2b
FROM defi/defichain:$branch

WORKDIR /app

# hardcoded version.txt
COPY version.txt /version.txt 

COPY genesis.json .
COPY meta.sh .

# Export the usual networking ports to allow outside access to the node.
EXPOSE 8554 8550 8551 18554 18550 18551 19554 19550 19551 20554 20550 20551

# ENTRYPOINT ["./meta.sh"]
ENTRYPOINT [ \
    "defid", \
    "-regtest", \
    "-ethstartstate=./genesis.json", \
    "-debug=rpc", \
    "-printtoconsole", \
    "-rpcallowip=0.0.0.0/0", \
    "-rpcbind=0.0.0.0", \
    "-masternode_operator=mswsMVsyGMj1FzDMbbxw2QW3KvQAv2FKiy", \
    "-masternode_owner=mwsZw8nF7pKxWH8eoKL9tPxTpaFkz7QeLU", \
    "-dummypos=0", \
    "-subsidytest=1", \
    "-txnotokens=0", \
    "-txindex=1", \
    "-amkheight=0", \
    "-bayfrontheight=1", \
    "-clarkequayheight=3", \
    "-dakotaheight=4", \
    "-dakotacrescentheight=5", \
    "-eunosheight=6", \
    "-eunospayaheight=7", \
    "-fortcanningheight=8", \
    "-fortcanningmuseumheight=9", \
    "-fortcanninghillheight=10", \
    "-fortcanningroadheight=11", \
    "-fortcanningcrunchheight=12", \
    "-fortcanningspringheight=13", \
    "-fortcanninggreatworldheight=14", \
    "-fortcanningepilogueheight=15", \
    "-grandcentralheight=16", \
    "-nextnetworkupgradeheight=17" \
    ]
