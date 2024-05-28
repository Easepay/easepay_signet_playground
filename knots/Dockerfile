# Dockerfile
FROM 1maa/bitcoin:v26.1.knots20240325

COPY knots.conf /etc/knots.conf

ENV PRIVATE_KEY=cRWA13VYwVPgkUTGMTxjeoLvsFd9TnH8BYQtyMVpjsn3N5SSitEg
ENV RPC_ADDR=knots
ENV RPC_PWD=easepay
ENV RPC_USER=easepay
ENV WALLET_NAME=GEO

ENTRYPOINT ["sh", "-c", "bitcoind -conf=/etc/knots.conf & sleep 5 && bitcoin-cli -rpcuser=$RPC_USER -rpcpassword=$RPC_PWD -rpcconnect=$RPC_ADDR -signet -named createwallet wallet_name=$WALLET_NAME descriptors=false && bitcoin-cli -rpcuser=$RPC_USER -rpcpassword=$RPC_PWD -rpcconnect=$RPC_ADDR -signet -named importprivkey $PRIVATE_KEY && wait"]