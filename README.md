# EtherEver-BlockScout7

logo 업데이트함. 블록스카우트 도커이미지 특성상 png를 온라인링크에서 따와야함
트랜잭션 업뎃수 update_sh를 통해 pm2로 관리해서 반영(그래프는 아직)
pm2 start update_stats.sh --interpreter bash --name update-stats




<br>
<br>

force fix SSL : ws->wss



도메인에 의한 탐색기 SSL 클라우드플레어 접속방법

그냥 원래의 도커컴포즈로 일단하고
fixed_env를 밀어넣는다
fixed_env
root@6029P:~/blockscout/docker-compose# cat fixed_envs.js
window.__envs = {
  NEXT_PUBLIC_APP_PROTOCOL: "https",
  NEXT_PUBLIC_VISUALIZE_API_HOST: "http://localhost:8081",
  NEXT_PUBLIC_NETWORK_CURRENCY_DECIMALS: "18",
  NEXT_PUBLIC_STATS_API_HOST: "https://ever-chain.xyz/stats_api",
  NEXT_PUBLIC_GIT_COMMIT_SHA: "95feb0ba",
  NEXT_PUBLIC_API_WEBSOCKET_PROTOCOL: "wss",
  NEXT_PUBLIC_NETWORK_CURRENCY_NAME: "Ether",
  NEXT_PUBLIC_NETWORK_CURRENCY_SYMBOL: "ETE",
  NEXT_PUBLIC_HOMEPAGE_CHARTS: "['daily_txs']",
  NEXT_PUBLIC_API_HOST: "ever-chain.xyz",
  NEXT_PUBLIC_APP_HOST: "ever-chain.xyz",
  NEXT_PUBLIC_API_BASE_PATH: "/",
  NEXT_PUBLIC_API_SPEC_URL: "https://raw.githubusercontent.com/blockscout/blockscout-api-v2-swagger/main/swagger.yaml",
  NEXT_PUBLIC_GIT_TAG: "v2.3.5",
  NEXT_PUBLIC_ICON_SPRITE_HASH: "9aac2f78",
  NEXT_PUBLIC_NETWORK_ID: "58051",
  NEXT_PUBLIC_API_PROTOCOL: "https",
  NEXT_PUBLIC_NETWORK_NAME: "EtherEver",
  NEXT_PUBLIC_NETWORK_RPC_URL: "https://ever-chain.xyz",
  NEXT_PUBLIC_IS_TESTNET: "false",
  NEXT_PUBLIC_NETWORK_SHORT_NAME: "Awesome chain",
}

밀어넣기
docker cp ./fixed_envs.js frontend:/app/public/assets/envs.js

확인
docker exec frontend cat /app/public/assets/envs.js
