---
title: The Tigers Guild NFT
tags: [Solidity, Web3js, python]
lang: fr
categories: [fr]
summary: The Tigers Guild had hired a bad developer for their smart contract. They hired me to redo their whole contract and achieve a successful launch.
thumbnail: 
---
## Contexte

Je me suis récemment intéressé à l'espace NFT et blockchain. J'ai appris à coder des contrats intelligents pour la blockchain Ethereum dans Solidity et j'avais besoin de trouver un projet sur lequel travailler pour compléter cette formation par une expérience réelle. C'est alors que j'ai rencontré [The Tigers Guild][1]. Ils avaient engagé un mauvais développeur pour leur contrat intelligent, qui les a laissés avec un lancement NFT raté, des jetons sans métadonnées visibles et une communauté déçue. Ils m'ont engagé en catastrophe pour réparer cela.

[1]: https://thetigersguild.com/ "Bienvenue dans la guilde des tigres - les premiers tigres entièrement animés en 3D à prendre le contrôle de la jungle !"

## Processus

J'ai commencé par m'assurer que je comprenais leurs besoins, ce que le contrat devait refléter, et toute fonctionnalité spécifique nécessaire. Ensuite, j'ai étudié plus en détail les interfaces concernées par le projet, principalement le contrat ERC 721, pour déterminer comment répondre à ces besoins dans ce cadre. J'ai ensuite développé le contrat selon les spécifications que j'ai déterminées, en prenant exemple sur d'autres contrats publiés comme Bored Apes Yacht Club, Cool Cats, et Boring Bananas. Ensuite, j'ai demandé à ma communauté de développeurs de revoir le contrat pour s'assurer qu'il ne contenait pas d'erreurs évidentes. Et enfin, j'ai guidé l'équipe dans la publication du contrat sur la blockchain Ethereum.

## Ce que j'ai appris

Bien sûr, comme toute première expérience, ce projet ne s'est pas déroulé sans accrocs, et j'ai beaucoup appris d'eux. Tout d'abord, le contrat. Le déploiement d'un *smart contract* n'est pas gratuit, il en coûte environ 0,08 ETH pour déployer un contrat standard sur la blochain Ethereum, ce qui se traduit par environ 150 USD (au moment de la rédaction). Cela signifie qu'un contrat qui échoue représente une grosse ponction sur le budget d'un individu. Il est donc capital de faire des tests **très approfondis** et de vérifier sur des réseaux de test avant de déployer un contrat. Il existe [plusieurs ressources][2] pour obtenir des ETH de test sur son portefeuille afin d'assurer un test correct, et [OpenSea][3], la plateforme numéro 1 de vente de NFT sur Ethereum propose une [façade gratuite sur les réseaux de test][4], qui est censée permettre aux développeurs de s'assurer que leurs NFT se monnayeront correctement et que leurs métadonnées seront correctement détectées par leur API.
Malheureusement, nous n'avons pas été en mesure de nous connecter correctement à la façade testnet d'OpenSea. Nos portefeuilles essayaient de s'y connecter avec nos comptes mainnet au lieu de testnet, ce qui nous a empêché de réaliser avant le déploiement final que les métadonnées de nos NFTs étaient invisibles pour OpenSea... Après avoir creusé plus intensément dans les logs de testnet, j'ai finalement compris que nos tokens n'exposaient pas leurs métadonnées au public à cause d'une simple erreur, j'avais oublié de surcharger la méthode les exposant, `tokenURI()`.

[2]: https://www.2key.network/blog-posts/what-is-ropsten-eth-and-how-can-i-get-some "Une liste de sites pour obtenir de l'ETH de test pour le réseau de test Ropsten"
[3]: https://opensea.io "Une place de marché peer-to-peer pour les NFTs, les objets numériques rares et les crypto-monnaies de collection. Achetez, vendez, mettez aux enchères et découvrez CryptoKitties, Decentraland, ..."
[4]: https://testnets.opensea.io/ "Une version de réseau de test de la place de marché peer-to-peer pour les NFTs, les objets numériques rares et les crypto-monnaies de collection. Achetez, vendez, mettez aux enchères et découvrez CryptoKitties, Decentraland, ..."

Au moment où j'ai réalisé cette première erreur, nous n'étions déjà plus qu'à 9 heures du lancement, ce qui nous amène à la deuxième chose très importante que j'ai apprise de ce projet, le déploiement d'un contrat prend du temps, tout comme la mise à jour de toutes les références Web3 à un contrat, surtout lorsque l'on travaille avec une équipe distante répartie dans le monde entier. Lorsque le contrat a finalement été corrigé et redéployé, le développeur backend n'était pas disponible pour mettre à jour les références dans l'ensemble du projet... Nous avons été obligés de reporter notre lancement pour nous assurer que le bon contrat était connecté à notre site web et que nos clients allaient effectivement *mint* le bon jeton.
Ce report du lancement nous a contraints à multiplier les cadeaux entre-temps, afin de maintenir l'engagement avec la communauté et de conserver sa confiance.

Et avec plus de cadeaux, nous avons appris quelque chose de très important. L'airdrop manuel est terriblement long et inefficace, en plus du coût en gaz de l'airdrop d'un grand nombre de jetons, dans un grand nombre de transactions... Il a fallu plusieurs jours pour réaliser les plus de 200 airdrops nécessaires, qui ont coûté près de 1 ou 2 ETH au total. L'ironie de la situation est que j'ai trouvé [une ressource pour faire des airdrop par lot][5] seulement quelques heures après que nous ayons finalement terminé les airdrop manuels. Je devrais maintenant être capable de gérer cela à l'avenir.

[5] : https://nft.multisender.app/ "Un outil pour faire un airdrop NFT par lot".
