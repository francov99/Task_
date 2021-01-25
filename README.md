# Create a new sidechain 

> I did this task from scratch in a virtual machine, so I needed to install all the dependencies including git.
```
Task: create a new sidechain
OS: UBUNTU V20.04.1
Zend_oo: v2.1.0-beta4
Sidechains SDK: v0.2.6
```

## Installing requeriments
### Install git 
```
$ sudo apt install git-all
```
### Install VSC for doc editing 
```
$ sudo snap install --classic code
```
### Install zend_oo dependencies 
```
$ sudo apt-get update
$ sudo apt-get -y upgrade
$ sudo apt-get -y install build-essential pkg-config libc6-dev m4 g++-multilib autoconf libtool ncurses-dev unzip git python zlib1g-dev bsdmainutils automake curl wget
```
### Install sidechains-sdk dependenciesu
```

Response
```
[INFO] 
[INFO] -----------------------< com.horizen:Sidechains >-----------------------
[INFO] Building Sidechains 0.2.6                                          [4/4]
[INFO] --------------------------------[ pom ]---------------------------------
[INFO] 
[INFO] --- maven-clean-plugin:2.5:clean (default-clean) @ Sidechains ---
[INFO] ------------------------------------------------------------------------
[INFO] Reactor Summary for Sidechains 0.2.6:
[INFO] 
[INFO] io.horizen:sidechains-sdk .......................... SUCCESS [05:44 min]
[INFO] sidechains-sdk-simpleapp ........................... SUCCESS [01:02 min]
[INFO] sidechains-sdk-scbootstrappingtools ................ SUCCESS [ 22.021 s]
[INFO] Sidechains ......................................... SUCCESS [  0.035 s]
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  07:11 min
[INFO] Finished at: 2021-01-24T11:11:34-06:00
[INFO] ------------------------------------------------------------------------
```
## Run Bootstraping tool
```
$ java -jar tools/sctool/target/sidechains-sdk-scbootstrappingtools-0.2.6.jar
```
## Generate keypairs for first Forger box in Sidechain
`generatekey {"seed":"bBnI9cogFBS5RGtw1Y2DZ3JysBDBwGny"}`

```
{"secret":"00c6741574c80427f8439d3532d0c42e922a5e56fcc2e6b4c0426d25cb9127256ee5ec954a2f23cef339fb67a9150d2801920902406d7de70d99c50982625f9dc8","publicKey":"e5ec954a2f23cef339fb67a9150d2801920902406d7de70d99c50982625f9dc8"}

```

`generateVrfKey {"seed":"8hwxwxr4Ju7x5pSeVSEEXX3E5sQr2vNY"}`

```
{"vrfSecret":"0300000060f85f2857af6a17100b6810d6ad9b0733b6740e49c58de2e9e6d2639b96799dc4ab46b9bfef0f4d0f66034f6cddbfc77488fead9592098c99f7713d3f3e52ad7d3144fdb5b7f4105fca99d35a3cbfe23a054189269d64db810275cfd2902e000080e01fab8918163b83c28ed1bb53ed249e50232117648834a2a6158f5520078e7fc3f84fb3e55154fcf90eba15843213a0060778033b96ae62e249515f73c37b9d0373abfb70f24e0c47f155d538733c451b21d7e120e14956d3d0734d130000e1d1ba1f71303d63788347eb5e308b6213d1241ade0bb68d4528b45f364297fb38fb2a6ce50f7127dbc31b2cf544a3c2cf613b6806a7cbdf7b9e9fa0c886dd1e02a60daed4390d511db1a41e6124497338b47320a70c6d3a71dde5f1bc54000000","vrfPublicKey":"80e01fab8918163b83c28ed1bb53ed249e50232117648834a2a6158f5520078e7fc3f84fb3e55154fcf90eba15843213a0060778033b96ae62e249515f73c37b9d0373abfb70f24e0c47f155d538733c451b21d7e120e14956d3d0734d130000e1d1ba1f71303d63788347eb5e308b6213d1241ade0bb68d4528b45f364297fb38fb2a6ce50f7127dbc31b2cf544a3c2cf613b6806a7cbdf7b9e9fa0c886dd1e02a60daed4390d511db1a41e6124497338b47320a70c6d3a71dde5f1bc54000000"}

```


`generateProofInfo {"seed":"rOPGKRJIYqYTQMNghYAUNYPGmTdwIHwY", "keyCount":7, "threshold":5}

```
{"threshold":5,"genSysConstant":"16acb86573b3a5bc0a5b6cf62cda6e8e355d20164697ea8f1e69d58cd5625a2d8b2da914a3b15c39249ef30ee249e76bff014a903c89372ebd9d755f288656c2dd3ae94f4c020e62a1c16ba24c59fad2461842c417d2cc02cfdfdd0da0700100","verificationKey":"5e7b462cc84ae0faaa5884bd5c4a5a5edf13db210599aeeb4d273c0f5f32967b7071ce2b4d490b9f08f6ce66a8405735c79197cd6773d1c5aeb2a38da1c102df07b05879c77198e5aafa7feed25d4137e86b3d98d9edd9547a460f1615b10000ee9570fbffedd44170477b37500a0a1cb3f94b6361f10f8a68c4075fbc17542d7174b3d95e12ddb8aea5d6b6c53c1df6c8f60010cd2e69902ba5e89e86747569463a23254730fc8d2aabf39648a505df9dcce461443b181ef3eda46074070000550836db2c97820971db6b1421e348d946ed4d3f255295abea46556615e3123de33ec56f784f70302901a4bc10c79c6a8b1e32477aeff9fba75876592981b678fc5a2703ac0b3055e567a6cb1ebab578fc4f9121fd968680250696cb85790000078fcfb60bdfc79aa1e377cb120480538e0236156f23129a88824ca5a1d77e371e5e98a16e6f32087c91aa02a4f5e00e412e515c3b678f6535141203c6886c637b626a2ada4062d037503359a680979091c68941a307db6e4ed8bc49d21b00002f0e6f88fb69309873fdefb015569e5511fb5399295204876543d065d177bf36ab79183a7c5e504b50691bc5b4ed0293324cfe2555d3fc8e39485822a90a91afcd4ef79ec3aefbd4cbe25cbccd802d8334ce1dce238c3f7505330a14615500001f89fbe1922ab3aa31a28fd29e19673714a7e48050dee59859d68345bb7bee7d5e888d8b798a58d7c650f9138304c05a92b668294c6114185ccb2c67ce0bbbb7e1dcbb6d76f5cacd7c9732a33b21d69bd7a28c9cca68b5735d50413862bc0100308bb0dd0bd53f3d1134966702dd3c7cc8b58b270a6996a646493250b0d5f3978d0c971f8fa7a0c958f3efe2fa5269244973fafb701c2eb66dd25901f93d677ab6c538c1ed11f115e52d3f2c7087ea40c3e8cd089376baa38842e9429b5f0000d19a8d874d791f952f13d3c8ecd92e44009c09815e5ae6a8e5def7ea52fe3de4accfb5ba2aa401fbcec14b069cd0dc0f66ab025b45ef9831a26acf58673db7487043654e7980fcb2b6c1bd7593a4dfff810436f653e309121c7ccf2df70b010000732254ec6df184be360cd9ed383ed7c8c236d7761cfc0ce4e7f0cac5a06f4edab9cfc75a7dc1449c0e18ed9564c974c2e1b6847c637f74e5d391cbc80fc6e672ffd66b5ce4fb73bda8359ab8a0ea1e855df1e07d82f93c935c7e1a9a55c5000065efdbb7c3e82291a482b2f24cbd46f4dd02c370cf6dcfe8fb3c00b8b004b5ad51369b1f1b134a824d1f16d72ca6a27ba2d6190150329139cf2c6d9e5a14722f8d39b96b882c1f60a7b230e929819e2abe1cd9d7f3e8c726b1a94d20c8010100732c396eca6ffa1bf851cef449f2f087edd93e4f641b4bd93a482d9f129e675aedb688993d4e2cee824d2803301364ba10fbb66895927adb53bad8aefe8a1caab6f4ccb45883e414a1223ac7f90a89087cd752dfa0c7b3e19bbae000edd5000028d1d23c627d1252d2a2a20a246af2280f50e3fde667873aadd9893ba6833118358398e7428e717128f764714a8d52b090c1f554f58e25ea815338d7bc7326c949567e74f2f2ab3c88f5075fea75594608b8937c9059a42d712ffbd1bd980100000000000250c1a474689e375a309446e5cdd3a0c26cecdcff5c7b8cdc0728868983f1a35a49e3a1bae6f969c3d47356c08d3d169d2c0a2be908d82cd35f41a23d8c2924a9f790ab3a00d53061d440a176670d6a32de2ecd19cf8a9774729c09a6ea4d0100d8838bf55d95521291da12294b302c66042eda0dc2acc79360a1fdd8c9a366fa790c52bf926c2d96b5ba88a3a443487c5235f7c476f350c2101cfbe3bd0361dd291ebc5e42c097a158704b71006886a3662ca6db7d816b4ad12444835d89000000795ce2b34aef921ccb3d9b9695f5d3fe0a03743c955cfcf01f8a1815a7c8b03de85fe15201d4b4b6f401cb334a6988ea5bde8986a468c47c3c6a5ae96a3160ff15e06699ea82bd40c0d5547fe1be77af7817861bbfcca3f4232f05a9cec800006c216565cee4d57b32d2d70bb3cb8d4a967c0eb5d7137b2ec58466f3d4d3b5375e4baa823bcc29c6ad877d9708cd5dc1c31fa3883a80710431110c4aa22e97b67fa639f54e86cfab87187011270139df7873bed12f6fb8cd9ab48f389338010000","schnorrKeys":[{"schnorrSecret":"04000000603f8fb6eca685dcb7eab8294ee7d9aa9580415231adcfef826e62722d6d2b8bef34deb823f249f06f632cf5ad1ef00912d954d3893b38e258e633354161ff0d4b25dfdda14dff2d945949e63f761e8735d4f6873f932b1ecb655d7fff08240100a705f629fe80fb7ed3f18019c02d429eac0ceccb33a2a72076cfcea0f33b9a0abab624f87f43749c0e059bdd1d773c8e184c0dc083b6262b7b73e936120d93e82708fb99cd086c86f8fcec005bcf4b591854169aaacb3d596a0cd70a615900003ae2827f384ff72004c6f218fee5d46b896139dbd247c6a3738bcca7143cb7ceebd13e1bb79a6d5ea64b660b66b3a986597ce27930cad3487cf11b2e7655082b40842f0289b08c65ee1caa7288ef3419bfefd376a78376e2c7999baa8129010000","schnorrPublicKey":"a705f629fe80fb7ed3f18019c02d429eac0ceccb33a2a72076cfcea0f33b9a0abab624f87f43749c0e059bdd1d773c8e184c0dc083b6262b7b73e936120d93e82708fb99cd086c86f8fcec005bcf4b591854169aaacb3d596a0cd70a615900003ae2827f384ff72004c6f218fee5d46b896139dbd247c6a3738bcca7143cb7ceebd13e1bb79a6d5ea64b660b66b3a986597ce27930cad3487cf11b2e7655082b40842f0289b08c65ee1caa7288ef3419bfefd376a78376e2c7999baa8129010000"},{"schnorrSecret":"0400000060a48f0195623b1a515ddbc5567c337bfed155f6b5cc122cac494a8ed32af4c4016df098972133ce6cfa87b298439103d2c2b2cbee933d2a4787fd49f46b1d181c2962ef590cfccdc022d0aa7209dd485ad83ecc9bb77c6185e8aa7d6950da000011cd55fca8121bad4797267bb734cbbe8da1459aec182ac63ce3bc9fcf72cdc2c3148af73fd74491413c6cae41b2a9039c0930e27c4e37b9ae427e1193a230c609e310a9d2185e967eff97f2df2f229132735055b44142235c6bb09fe6300100485f73c2bdb9a84bc9fed364eb21403446dd642defc04a5206fe8b965c085ee5e4889de8f0e43e3caa08c3b81881fcc971557b4ac9670f49bf0ce1cd2bf66a3fc375aae86980af2b5d9bbbc78bb92c0a10f10bfdb99058db60bbe7d9d61b010000","schnorrPublicKey":"11cd55fca8121bad4797267bb734cbbe8da1459aec182ac63ce3bc9fcf72cdc2c3148af73fd74491413c6cae41b2a9039c0930e27c4e37b9ae427e1193a230c609e310a9d2185e967eff97f2df2f229132735055b44142235c6bb09fe6300100485f73c2bdb9a84bc9fed364eb21403446dd642defc04a5206fe8b965c085ee5e4889de8f0e43e3caa08c3b81881fcc971557b4ac9670f49bf0ce1cd2bf66a3fc375aae86980af2b5d9bbbc78bb92c0a10f10bfdb99058db60bbe7d9d61b010000"},{"schnorrSecret":"0400000060f1e6c2b1e5dc77e70849d5ae27341eae5936d7a0dd8c6695d3b80df1ae9f05d44fcd8b68e67b05302b66fa2afb512f5332ed1c1e85dfc49b96205f9cdceb533304f724b531d87bf6695db2b060925312be7c60e32f1059405755d9619a6d01002bcfd040f4a03f92ccb668b02b1a72f68fb0e114747628797de74d3f28602f1fd455dee343a184ef6479757e5e6eb31f85f564ca8b19a5ffca7e992f9eac5fb6e2f43521047f3bf7ba7d9d57dee6b29f00d8578cc61eaeea17b73235fc1e00009bdf28b33012ed562fa364632198b98eb67510f99773bb8c8da712511e205255a1aba713919720fdf65752ed1019ebf355f2adc12448e7066e7714d4892111d97c35075e3c30ade8e7dc3410e9047393d8828bd91ad8e71015eb410ab1bc000000","schnorrPublicKey":"2bcfd040f4a03f92ccb668b02b1a72f68fb0e114747628797de74d3f28602f1fd455dee343a184ef6479757e5e6eb31f85f564ca8b19a5ffca7e992f9eac5fb6e2f43521047f3bf7ba7d9d57dee6b29f00d8578cc61eaeea17b73235fc1e00009bdf28b33012ed562fa364632198b98eb67510f99773bb8c8da712511e205255a1aba713919720fdf65752ed1019ebf355f2adc12448e7066e7714d4892111d97c35075e3c30ade8e7dc3410e9047393d8828bd91ad8e71015eb410ab1bc000000"},{"schnorrSecret":"0400000060ad46e7fcc7da6d2f4cd04188e13e665c173ffd01a9442df65a633161891183e27c9ac5c122aa4d0c08725e160528d43148268741334be4b292ea6ef3058e92be13926804ef27ec0fb1b6a026f02405df815085ffd1946107f8f7e04b277800004c8446258a4c0f3eea681de70c7820f1f3db2e2aec7d516a4b59dd3a5134b00839aa6e4f320c2e6b400cfe84bbc9b0d4eb29ac84e3d9811b56a6e6e5d8448da183bce7566620963ee47d70391a25df9ebc8ce9d3840ccac8236f948a67e10000c210dc5e0d5283e5d6662282e91b325c8ee42fdfa80523b378e0cab3e2046a362b4efb9671c265784fd3b0a835c13b72d1c97e487e8138eb5786e226852432de862184be06cd1e7b9c6cea2830c00762395e6c3d6810a857e6ffac4d2e0a010000","schnorrPublicKey":"4c8446258a4c0f3eea681de70c7820f1f3db2e2aec7d516a4b59dd3a5134b00839aa6e4f320c2e6b400cfe84bbc9b0d4eb29ac84e3d9811b56a6e6e5d8448da183bce7566620963ee47d70391a25df9ebc8ce9d3840ccac8236f948a67e10000c210dc5e0d5283e5d6662282e91b325c8ee42fdfa80523b378e0cab3e2046a362b4efb9671c265784fd3b0a835c13b72d1c97e487e8138eb5786e226852432de862184be06cd1e7b9c6cea2830c00762395e6c3d6810a857e6ffac4d2e0a010000"},{"schnorrSecret":"04000000608a31ce97519ab975c3a24eb5dc62e361ec6dc08e8d24ea7f481f6a66b52b2977ebf531dbbfebc9968923734abf085771396be6c58ce76450364503f6e0df319ba545766d2651b1f545ad73905d49023a0ffac2829ca390fe68360798557d0000a167868bec6f95eac2e1b7e77df321e9bede89ffd0ffe6168db5f6294b292d8fd0bda44062c5897f78cf256d213a665784db80443819dab54bb6554debbbc9ba33c15a94ddae34af443d10d4422076208572f655d75a51087148ccc92e8b0000da5853499b61177c21e065388e3b694ebc4a053f4ae0b63d15bbacace2ca5eda3d633520395a54f62be4b397c91d30e7e7bd8b4b061a604303572e6e65b77dcd622254de86518d37b25902517428ed9223419903130b2b553a01dc6b6281000000","schnorrPublicKey":"a167868bec6f95eac2e1b7e77df321e9bede89ffd0ffe6168db5f6294b292d8fd0bda44062c5897f78cf256d213a665784db80443819dab54bb6554debbbc9ba33c15a94ddae34af443d10d4422076208572f655d75a51087148ccc92e8b0000da5853499b61177c21e065388e3b694ebc4a053f4ae0b63d15bbacace2ca5eda3d633520395a54f62be4b397c91d30e7e7bd8b4b061a604303572e6e65b77dcd622254de86518d37b25902517428ed9223419903130b2b553a01dc6b6281000000"},{"schnorrSecret":"0400000060e83ee279fdb07019ce8ebd79ad35270e5504513d827e0807e43ad24d083ba64898853b9f4729cc6db0d0e5745450618ee29cba713ee15f366b87ba55f6c301ac3706b38097ed6bb886f706dc986e0eee62b7e9d62008af89dba135a1693301003bab8442bcf06cee6b96b6032763401f1434aa70eb8af0478d7386d7b88412d197d34adc52c75e8aa5d5f1700838d595b0bf376762ca5c6e4fcee7601443ee3d297fe22feeda569a0c6befae16658b170cbd57f13b5b53d6db06fc0302a00100708357646e0d6a85d6eaffd325b0249022512756c292633d757715c7ac02c4aef94284bee3a1a441313f85d1226e03a98142cb34b83b7ecb24b04fa3b5a529ca167953d6826f0da3cb88ba8116f6597e5fcb910e4d960033b3deabfca122010000","schnorrPublicKey":"3bab8442bcf06cee6b96b6032763401f1434aa70eb8af0478d7386d7b88412d197d34adc52c75e8aa5d5f1700838d595b0bf376762ca5c6e4fcee7601443ee3d297fe22feeda569a0c6befae16658b170cbd57f13b5b53d6db06fc0302a00100708357646e0d6a85d6eaffd325b0249022512756c292633d757715c7ac02c4aef94284bee3a1a441313f85d1226e03a98142cb34b83b7ecb24b04fa3b5a529ca167953d6826f0da3cb88ba8116f6597e5fcb910e4d960033b3deabfca122010000"},{"schnorrSecret":"0400000060ff87b463fe9ad4223ed2cd1b7ded0f8e2180c3908e40f5f3a4999af84fecc74551439a5c01c80f143536b95a508529d456f55ee0709eef1b649de4dc486bc1fae64e9873273f5a2eee2bc978eba2e72d286ba4bb18eb1ddc29170f761d1c00003439929ee950e3a5135c9082cd71535ef3f5811f9544f08ff12cbb4be80957d615a7574ff0e0812abaff4067928ea706a5ca943f9473c5bd0b41b12cc2a99777abfab96900881eff2e1437478f5075a8610b7b647ce62683c1ef67cd01e800008929fd3c27a947b7b438acca3d30dd07dbdb89728e6b5f93ab1a79eae5b3fc9fe971e4508cabbe95f4f37ab97e28fbd36d20d8f35e75d4a2506418859ed1de0572039a5156232b078f32f1ca80a85befdb76980093a09649a6e3650ba603000000","schnorrPublicKey":"3439929ee950e3a5135c9082cd71535ef3f5811f9544f08ff12cbb4be80957d615a7574ff0e0812abaff4067928ea706a5ca943f9473c5bd0b41b12cc2a99777abfab96900881eff2e1437478f5075a8610b7b647ce62683c1ef67cd01e800008929fd3c27a947b7b438acca3d30dd07dbdb89728e6b5f93ab1a79eae5b3fc9fe971e4508cabbe95f4f37ab97e28fbd36d20d8f35e75d4a2506418859ed1de0572039a5156232b078f32f1ca80a85befdb76980093a09649a6e3650ba603000000"}]}
```

## Setup local zen node

Generate data

```
$ ./src/zen-cli -regtest generate 220
```
```
[
  "0c0731fb66c96def26c0decf1dffdd1fe5dbe1598626ea61fd69eb3dcdb7946a",
  "0d2d6b6326370590b8f969a0cb5eb98126a6dd552cbd6623f91d314b1111d746",
  "0de0c6ff9164feff3ea519218d4e2dada8fe79a334c7f6036b19e02601e3174e",
  "0d2aef7e462e535a96b74318ceba6f69b61de31abc9fe08450ee0ff2804cff97",
  "04e0853f4d2221bbac57b00d3064ccc585c6c4bd216eb00530dce405d1c9159d",
  "06c585c1aa3b9df7fdda1db70b6ff7beb0098dc27212ba5750156a7b3ed0e519",
  "01bf5efa843471f3bd13f2ab929331d967c4bd74ea2f0fd63c0003a0da850413",
  "0d321639bb7e0bedc2dcf497930e170cdad41d4c5e81b38d58b9f2e15768eca2",
  "0842c58aead341dbbd8040af23d7e85921b9715626f81cad181daf3d67c8e3c2",
  "06380b0d18531d470559e471c5b484c6c21ab34e933f52571e24da999757f319",
  "0ec432a7c42d65683ce9405d44ae9ffc5aa74661bc3129078275b15ac5f9d648",
  "04c98f491691c07e8684f4421773411bc2a20cea60e8b70759f1dbf8897775c8",
  "0957188e737a92f08097145fc1f6305e3b07d83095dba1d122760589826b6204",
  "0c906691eccc7581deff4fe226fc6a74f83d666938585833ad2b595b93fc3da4",
  "04b8ddc3aaef2a3cd4b97b6c96c9c750ad6c551703515bbcd0f4f52499bca74d",
  "0483ca563b0cc53938c278447333dec612e666bde04e55ceb0a9604a00e49b51",
  "0d3c1a526a4d152b6847fece6b0ba90bf1f17c664be92815b2f2f4e369246827",
  "0011680c915d2fdf28d134a4b0320f362d32d3f85f170f7564e332c697f84b2d",
  "05df4ba4ec0aa9ff7a3dae1436f0c4ab98e00a18981bb0e63d53ebc3d7443fbd",
  "0db3698be2b49323f9e4b1c47f5c0950485e2316629c96d1b26579fc1d562144",
  "0a4e2e6bfa23b7a4eddaa05defff913966170af0c522967ae83ecc6ebe5e9023",
  "0de022c1288761be532fa0133312a9c01fc3b2342ba90f30132a18f4314d9358",
  "0b3c4f0bb35c5206c8117bba2409803a1b44d69ed0b40f72471ef4c71e302f35",
  "06ce4351357fdd9e69ad64c350701868cb7df5e0a3baff20fc651da8770742d1",
  "08eda3d3a9b88d3b84696c96cf92913d37635137528d1e0ccca371d3fd17ec71",
  "00bfe9f6d99eadedcbd83159870a8a179687c27b9c4e226a80bf4d21f7f21ecc",
  "07ca3b065633cad63af88044debe125773b9e446b993bdc57b75b72433cfe5f4",
  "015a06c4c27c75d561284e04392f3b75c355761f35ce3f63b55e9bd7a83a6482",
  "056a3818e7c4a8ac699a7e9e88e4afde6c8edac7d7b98db9a1fffd653a7cea93",
  "03a6a505b7295b8614a1734012ad04ae0ddc71b90ab9500b0e72618df32907a7",
  "00dec51659433aea1c7416e0527f9d5ee3c012588e9d7d5ee2a3cd7c85de01fa",
  "0982eda1092e96fb403e43db0872fc4ae69b9eb6b3ccda3d315fa39b785cf546",
  "03a217b4f056586b846e5abeffe2c4b90684a8cb681dac69b489534a049cdc5c",
  "0c8f1623177f5a25fda0e9296aa70ac3e439b3814d14139d4e0eee3de1291304",
  "0a8a8a9daab69e7f3c263e20847a56f0ca6716f8cd9137807d339c382c159b3e",
  "09a862721890c55546963b44b8af576da9aca527902a5ec01ba5de77f5883d53",
  "0eea81c28f9d922d8865230dee7901a14156d579963975b644be36c15a4bf6c5",
  "004c27b77d64cb7bcd1d6ad90d90d38e3e6b8294bc9a843469bf1d9a13c1e8c6",
  "045dd4cb5212ad93e89491b9f02bfe3e7a0573ece8b7954a119c22bf41b10ab4",
  "0500898d49f01b64af38a8efeed46cfdc64007933b6dd86b32210c7746172616",
  "01961e85ec63bffb9de017ad596e7de12253e812d24e690a9d4061a1990f525e",
  "018cc6c91c0dea1ede97e756d5ed2e61ff266c1a055a7455e633a23e2cd90fe9",
  "062292f12aa53eac962e440b76af7a4d87bf3bfafa4c893df3d7489d991356d7",
  "0b79a28159b796916c8289a61bf5b1bc2014ff8a0dd6c228da4d49228da1a96c",
  "089d9b2459530d9539bde473c5876f4452b5e36a4b106c5c89b3197bdf7dde28",
  "031e248ae615f1c3a3d50659d6dfda6e57506d1af75f54a3c78970921ce0798c",
  "00860977e53a724fd1a9d476170e274c96a46bd6fa37d5b69e73b31183808664",
  "0298290319cb2e8630b2660e1cab727ad022297c3845dddce8986f123d946239",
  "0071de35f8f72d7a1333f8dd69effc682b282b563e14b177574ac5c454b5d919",
  "0e59e93d9b925cd93d7481cee144dcaa9dc7f3e9515fde76fd2a4a5d8c7badc0",
  "02a64fb8863955acdd0d41c6cc86aea3e950301184714d1cf6ccf433b2bf61b7",
  "037a2bef2a69625127877432cb2aa46f4aabf9067061fcbc32a34212c37512ea",
  "08659f20d4b48701df48b3365dc6183aefa53460d66a09a90bb88068ab3d4a99",
  "004c0621ebc5b12c94461716a78cfe39247964a7d143c66a133e80f034b3fb2f",
  "046b7ee28ce796b5dfa9a4f92ee1a710b6a545232f4ba97a35e3cf9eda38e18e",
  "0bc60d623bbe1888a85030b366eed00846796f7fd8c43fd25bb1ee0e024e6f01",
  "01d30058a71b7022adabdd3b14aaa8846312b70c5e641767efcf740ce3998e21",
  "0bf483e88b3cbab011d66bfe58753ab1c4c7c07bfbe323745f541428ab72cf3b",
  "09a85c843f92e00de1ba5ddf80c81662ff196c013ca212b374bb6cae32b1e59c",
  "004293accca56ad19055ab9a403613b017e2565077b27d345d5dfb13d67314f5",
  "08fdd3b5b380865e7e23c3a2d957cd761ccf3fb825033dbb1ae0516155477a9c",
  "0ed0b417b83eca0ad64a7b648223ea523a19aa6918949079ddd35dcea0e6c262",
  "061bc12a0eee6960cad76f3c1b5d05eaf05cb2cfe812e6b0be8ca2d6c9059048",
  "06c70dc6ef14eebce770b5865277ecf52355112e4dde153b6c97a5df39a5d676",
  "0e07a9c6c843901c1b64ec6472fc9d753a81ea3b312af223d06e8e41bb707148",
  "07d9a3e5a88437df4ff74e6f783e1882732c6b543c5f509db826daaa9798f736",
  "097f220f0787b1170273b031a644f09029dd31db8c507d8cb3751d2777e89d9b",
  "07588e137c8d5c77241109005e611ca8df08f50bce2326a9612bcec85fb8103f",
  "0c20b95747064ab275593fe567575a9fc25c159f5a02d4a130d662e0a2bc04e9",
  "028db635585e381e600773ffd1de1d4fe49fef3497a467cfc39926214636f728",
  "083268b976ea23e63678ed51b997d4d0e1209577781d479b459ea4ed459e53e6",
  "0d11ee99fadf2af73222d65a19b6a95c9d96136d079ce2b455b14128b83e8761",
  "0173996526b1aed3c2bc774f8149551d31b43d7a52136054ded392cecd33e09a",
  "071898fd26044d795f6ef69b394eb736ac13db4d1215a96d9db9168c9ebd404a",
  "0bbae65ca1058214a27e242ce5f7369b50d5af32725d5d8b247e557df8b8f227",
  "097648bf7e95c4aadd6544b3fd4d898deab7cb3a1757dff2d8afbbe703f5614e",
  "0d8445aefd439e4f5994d5194544528fe2b3e9d787a38c54bb0be023ee454937",
  "0b9191dbead2f54da468fe20f2de5a892c90805fd4912410f267cfe7f97ec3c6",
  "05676c7e23a836085ecacaa2acb0b58ca38f2d262650077d286a3d45439764e7",
  "08d9d81b6ee4f7cf83be5a7bf80e3b9c6b728608f001e58d2554eba553185b13",
  "0ee054e5ec5b454b7d0c6692b27ae4246d6861f90921a6808c7c14b32f863722",
  "0c7520911b7b9303dd4d1c30ff15077550dc420a3d40e3f23dd9bee6106d5506",
  "081d413d15c1e2036c16eb1221203657749716d1a3437f894a4e3564030de068",
  "07e2701b8a9928a772d3947e160e03c4a8da2dc9f81cd533e14e3183129f072a",
  "09b5d9c795ec5036428d66a768ba2a3befc3fe07a140c4cae2926e3a1e1b36e9",
  "097f8122b447fcc567bf08073bce332d542d0879b1481306a2c429218b18a1d2",
  "01c8730ee29d97f27dd91a28030d64f1c7ea3b4e1eac2325ac35cb3459c0c23f",
  "09090961fa6a4188a0c494c5553f9529c66ddf4f9b7affd4a82477857ac4d1d3",
  "0745a63c2814a8e95b1c1bf966eb327d4104c32c52f0757501f005a26b2391b6",
  "0aea131f6f8f4393c18a8021f4993ad2cd9b7fca3a0d000822ad1fdea5b9d159",
  "01bf6a2ae8534b1da79f1e202c55978f1dec66ebd3997cfb47b5c161492e59c8",
  "0a11ea4783ade72544eec890a15e3285bda4d256191589f4cac918f32f8fe3d4",
  "0bc42e7158d18c8efa437ff224249ad26336a8d9ec7819828e1134dafe820742",
  "0876ca19d9ed9dbbca648c1fc14f77144da9e557d2ef1911bdddb7a9c4f0c4af",
  "04b7427d42da4ef02aa833d5b389081ecdfd137c6d7dd09ebb63439a1f0ee8ca",
  "0c5a28fc38812be58d64985f50efa099a4ecee30178696134e45f3afe7e3461e",
  "01ff9be0c625ad88e38c31890839c1bd3624749eaa5e422a27e4f47aee23fd29",
  "0abf294b5f8e153c8da8c81ed20f36d5bd46862bee1784b3228c77825d539b11",
  "077d13fa0b909f7df0b0ab425151228c3910acfcf04a29d609c5ca0c4f147b18",
  "06b254906d869a704215d1a3e67f603983de6111a816121ddc3ad6b8430d8113",
  "0d4b5e743dd19c3d5cc034ffff996e26b902167de87533dc24fba518611cda39",
  "057f012a4066156b3da00d428e3cc98cb00a6b8799fa7d8905c9e7196dad4c13",
  "0897293002376561853f1b7777a2dada23d979a0d32cd3923a750a5aa2055e6a",
  "0c0e5d1e8d39aeea4145a112c3c1057c355f16e87ecfe272124d470a96c32e53",
  "02b9769ced3c007d9f2418100ecd3b45c42d584847d08ece0bb02b2621650fa0",
  "0e518f424396277f7a788c386100a6c8c67da512056e03373dc5ab30ca0a0b4b",
  "0daafe806bbc0e992fd1419af296cfdabe1c8bdd90db0b7d1f089057bf6005f5",
  "0973879689758cbf9c6e405dc4c180207e374c762248fa89fc0a856e9b8ef504",
  "0b2685c38830e85e90301c4ee6bdc395f21bbef1158cb50c1636f5f6e74f904d",
  "0ef27517c7e8b0a969c6dbb901f34dfae069fee7035a0656ac51dbf3025dd75d",
  "025f95d3560d884033fee71436d37fcb91bcc46ba16b9b8360579cb3306c9148",
  "0e807147dd25aa2b8a8c0baf8548d2d2dd4f55816e05c3bcb2301ba29fd1640f",
  "09111f42c75365745ce977afb218b2b415a098a245ce88c1c989f77953e2e1bb",
  "0c9e85b02d1bd7f2fd5254107fc295f6c74cf406fb804b5255b63d4293c3f3c6",
  "012e3b1e59db79dd90f1c8b99a581ecbf9761a1070ce569dcf1a80a70b5138a4",
  "00d82fcf559aea727fa5a151ec8159516c2854ae3caedfc3bc6e14d98bc34eb7",
  "0538fa167b548c667c771f97a50b1a4d93390c67f1c1b9792283ffc33cd3de41",
  "0cae829325fc0ee06f6f80f5bf867ac353b5561f05ff3160a9efe8fd27f54f11",
  "0314366fd8cae56f0f8c7a3da17d91fbb33f4b3dd7c38932a90b2185854371b3",
  "0853b4c9d38507c082f6d596172384fe6650ea8095b51e0a9d26d473ea3c39c2",
  "0e7341d42a0a59469c7d18a55141273f4b6d05a64781af1459eb211326f59898",
  "0db5f3d030a0b98ec3708181aec9028ca25deb25fd99744a744c3a382761d9eb",
  "02ec3a5183902cd8adf4e995b6ce722c825f08d8f18b46530c28323cde9f5825",
  "02e593fb7f603a46b05dd0cb13e87137c545d2a5044002828087b8768245538f",
  "06db0a2438e45cd4fe24dbdbe7e68e7afb0ef7de581f349b8000fa57872eb275",
  "0e0bd383d050f2f257aac18d6f16675b6b5826cfea4f3b8f100cbf493e9ae58b",
  "0728535beff33bbd86bbf58292cd455d8d2e7ed0e0bb3b0c49a3fb427ab427c5",
  "0b71a9256dbf50ead2063b5a62c81434cc1abbb18c0ffff5b802b6d714167b18",
  "0d4e34c66191d77ab68c9efc2e5ab68a3d408895031271a784bcc3c9c52bfbea",
  "05a624b67a059edb97ca59bfc30c302f3018d2341018d8b57266bf45898c1a2c",
  "091085ce3bbb8f46a25fed9a713cfd506ea32aca8e35d423a538f1852e2e629a",
  "079b049eac3a1b8308318876b383e8ce979e994f31fdb336ff52a8f2a711a7ca",
  "0da52cda3160f8659cd121459939b74809b17605ee3ce255e0e86f84be68940d",
  "01f0293b86008095343b2522851e7954e29e4f9dc85e6ee869d65b27fcebf046",
  "0c0ea325eb71b052bfc60f3384b5bf7a9d085ae1e35562301ff1fb90d6752254",
  "066152154097905322e4a079adc712ac3a1d94f5d5a181511337c8fb8ddb0714",
  "016d4daf03514c645ae05ccc36d1ed74d1986b0b00e966b3388690e51c04b159",
  "0e10cec863b3c31b4eea5e049523310e84f76dba3e257122e20f5a994ee71b7b",
  "0e19219abd2b132a00f9a741b476585ce70d244159cdf08a15d81a652b644ce2",
  "03695ef15974da876b533ad4b589c351d4b60ac760f9ed56037829bca2dcd509",
  "0a39838f824ebed29da653261259057dd4d0b32edd9bb48876c23800f4882954",
  "005f5d8ddf90568556fa3c3bbe6b86df2bb3f51e2186543f6df0b7ca4afe257b",
  "0e06e93c9456e29c24154f849c8a200d3e4053c44e71503e734a03764d7dac74",
  "06f71fcdfa2ee3ae20c811c373a771599d922cbeff315a106d5d02390809e8cb",
  "00d3e76425b247dcb3971287fe3da111de39c28ce427a10bab33f9cafe960573",
  "0f021ea97acee4aa43504268b066f50d267bb6b0c536beae651245dd127c003f",
  "03d5727b0515697f5bd916958c614c5b50e43faf4c7d367c8e7182af45a60c6f",
  "087cdfb03724d3786d961e74d5920e22bca1c23724fae40c6378cd35b245eba2",
  "044c39509a9b116dc40d84b1b77129ffcf8ce29212a1426539f125956078bdea",
  "0a5dd794cd561b3ab66dd94409b87d26ea2eca922f75b2e71f9920b973b27fb6",
  "0a6bbad9bcbbe4b03687b8e9e1af9c946af056711ed5dfb815cb56526722c80d",
  "0587d72e91b4da23b18e11dc937a506d777defbe1a76b7bfb1377e3746e313b5",
  "076bc58f3b879eb8dc16d11a69863eb88659c12083c03b379c743ab52b82d9ab",
  "06bbef9c0a60afe5c40d57932f7c8df96ffb5fce293300f872c43b01c5ee9f76",
  "00ed5bba9fd9702d6a6eebe99f740e5d113c7df003ff4e094f5002a7ac0fe1f4",
  "08baf82b2ebf3096ec161e332708c2c884281c0e3b34ccfaddbc98ef26f3edef",
  "097315df739bce59276c9acad7710c167ce663cd6a92273d6de501f98072e07d",
  "02b536d88e6662b092294612569b35cffa891f8d3429cef67f968ddb09272f6e",
  "09c657ba5a37cb9e01054c95bd651d143295134a3bd2e74da8faf68005a449ef",
  "076beb5ffafb01b3dae60feb421b6020b443dd789c88aa1a6dedc8ea7fd4b9ef",
  "02f0397ff07b96a7b26900fb134b38611a28a5a95375ed77f93f98daad1a7f6d",
  "057dc127acce45b1af4bbfcf162a9136472011aa5c04677422b56f798cd44364",
  "09b959939e79cfb1279f730d666acb9313fbe85a88c1191a235b376da0e7e1d2",
  "058c702b7ff068eb4abb4cc83fd905afa118bc114f86d39087ff30cd51cbc1d7",
  "0c6dd9da5c1590030479c6b823f1bd1867a3b8937d3186125edd9faf956d0a42",
  "0127b27b7d80d6ba3c00d72009fb0088ac480a8eeb25d620248ae7288857b293",
  "06ca5c67bfb81210dd5cd546aa0d5da28fd3acec7181acf0a7a5fc1b4c7fca1e",
  "0d5bbacb2a1a9143f4101e16da5c02e0e09c1ba553af6bcf7d69f8ea90298f17",
  "05d131ff0c1d1fdc600640666803dc824a60aa892e9a53f25af8bbd89733a66b",
  "057aa04a12938584baf866e9e164a0237df63eef1bed611973e78eeee26c9d49",
  "0a8c838f6a8bc09a4c3daeba23e3f299e305ddc7d0f79a87718a7a6657ddb184",
  "0d88e00cb60829bdcd4039915804e34a1268d9b2967eec92e1235a2b5aa7cbcb",
  "0be54818d35732fdab8fdeddd41dc52bb2951e7cab799a3b493913e2a85c0d06",
  "0976f98dbdcc8cfe38014a3e2f0a703e5fd481feb63a656ae14b99fd39bc6ec6",
  "0f0a13cb26cf2f3fb4007623ef2b18dbde5942d45cb5a7d4a7b1dd9c259872a7",
  "099dfa525d1616c55bc2ba41307cf904d538e7a7b134683afbb95dc8a871c1f3",
  "0e6e0fcca27d646361de2587bf52f35a444ea5b759ba09e6cc7751f3a1433f3d",
  "0394378982058de9c4f876315876ea880606b4ee87df45fa6b585b57f34aabfa",
  "05c5a59966a9802217783293a3ef95b2fb45cdd4f55114441ab33fe2de8bc18d",
  "052b9f3ab877a9d8551defe3fc61a99412eaac2273704a0d2860567654705059",
  "0f08604392031d14f8be3266c5bc2f51d1ddb8322bca9aa8b5cf8a12cb8fbe7c",
  "00adcd92b26695b4d8f3e50d076b32ff09e1b1a7823d73a47aa779f00a443923",
  "0410d1dd8591fd6bbdcc7d50ad486a33879856ae54e809c2df740cfc72f2b256",
  "0bc97ccbdf976292f3fbc120d86bf55c96e5f20f1aa1b413d6a9d2c28668cd3c",
  "047d518cd6daefd53e788b40effc969963ca3dbd16f78fcb9ead8dcac10d989e",
  "0a6cb9915fe7064ee8590fe2b74fdb0ac65c2854bf394ce85ab3f4b3c6108399",
  "09717bb14a12bc88b0597a12da4f57162108e7ee2d2df7c02c2ff4186ba1b0d9",
  "0cff230fe692b499be46de29d5a0ff0371fef25b81733a38eddb330c3de30530",
  "0140aea109d2d6652debc66c3b622d979c7baafbfd868407f2b50c36c5922b64",
  "01dee457e37bd9ad01d611bb3180ec49623e2acf7898842c3b2bbcbac7ecd9a8",
  "0e3f3f0ab3d0224858c9c3c9f92fb078e4f8c8708c08c7a24fcb27710ddf39e9",
  "0276ffd8275b93b78f662cb4d040241fbf097bf40fd4fbb1df22c3c45a268536",
  "00ffa4e1be9fc8b69811d113b5b4d38c2fe465b0d023003ed378d7948e958b76",
  "0e8f974690b122db47b03936a33d00d1644a99bf66d752128754b0ce0495e597",
  "0043f43305c10f33969fc8e20bb93db5e09ffaf21b659a7fe9abd3abb3566996",
  "0ae0b9aad84cdcef414c60a960e45530c644bf94ad7662baa255e13253223fdb",
  "0c3b79029da1e72d7317e548dc5b898b3ee85a86a8466bcb2c891f87d211d6df",
  "0bc9bbe3fff773eaac1da88107495c44a31f54dac8b17fa0300dfd7a7b26f4fe",
  "05118fe88a7b7ef22b0706634ada183451a8ee280a72c258a7a7da8b53f8668c",
  "012a18da10a13645e90ac2344137a12a9bbf9ec945244763f8e6978f55c86200",
  "04ae9a19ae123fdf4bb726a51af609ed23fee7efe30a2590a22f9caf74b3c35c",
  "0def9f843f211d2791f7157eb5647090a6ae95f0aab7b58827c8f1dfd5381671",
  "04ffbf2d08a2b3a9e1d647e9fbf952338ce69933bf53145d730175fab2f12e17",
  "055cca8ff7a024099751ca146d92c47e0911042db2c5f54c6a62dc5dc8f55db7",
  "084199c2223f059bab1291ae892e707b56cce54173617444730bc14b7060e231",
  "05f07362b0195480285a27bd06d07dae77adfb06513182d6f2dd1b1b4f728a95",
  "02969146e2ed7563b3203bccfec10e8ef2e051a072a28e78f58c2c11720befaa",
  "05c8b87e53cadd46a2ccb6a3cee0058725b10ef4ad9896bb8663fdca8d967beb",
  "0958c6669ceddd06d413aca14ba0e39aadafb47f01f45c00cea3787eef55b656",
  "074c49bf1100960f144ba01ad5d4768789e2206db4c3723f069dbe798300c86c",
  "0d458287a07e7cb8149623207ebabafa0c5fd722f2119d41e99b7ebd7dcc694b",
  "0e13355d8547ceec6866b0e5385e4d285d9fea90036e1a988ff5e9e758aaa105",
  "09b0164701738bda860e6c031cd59e1c325df89b8eb0757b0c7566fe051416e8",
  "054caddac2a1cc22331215f8ab41e35f3f4ba77c34e6aecfe6526598d84240a4",
  "052c9c635f5a6c47400f15063bb9b67a683d02c4c3975730e28a74e8c0eb1dec",
  "0011f11b14a696eafe6e66c3a5df286881010184cb45ecf473a370cc60e08ffe",
  "08c44cb0783445a27a1dd822f61f67eb00d4a4f2e1f6b0898f765d180353efd6",
  "0e0ad2efc23ac54f32077a84da700788bf5ac7f22402c606aed07b7dd9600a11",
  "03d6ca4da561450f73267567da90d854f8b6457b84aed9a419743aaa9ff3d414",
  "0cbf51d8b0155e2dafbfa302bcd3d318a5a6e94132eb6d031b4df6108394ae14"
]
```

## Sidechain declaration in a Mainchain node

```
$ ./src/ -regtest sc_create 10 "e5ec954a2f23cef339fb67a9150d2801920902406d7de70d99c50982625f9dc8" 10 "80e01fab8918163b83c28ed1bb53ed249e50232117648834a2a6158f5520078e7fc3f84fb3e55154fcf90eba15843213a0060778033b96ae62e249515f73c37b9d0373abfb70f24e0c47f155d538733c451b21d7e120e14956d3d0734d130000e1d1ba1f71303d63788347eb5e308b6213d1241ade0bb68d4528b45f364297fb38fb2a6ce50f7127dbc31b2cf544a3c2cf613b6806a7cbdf7b9e9fa0c886dd1e02a60daed4390d511db1a41e6124497338b47320a70c6d3a71dde5f1bc54000000" "16acb86573b3a5bc0a5b6cf62cda6e8e355d20164697ea8f1e69d58cd5625a2d8b2da914a3b15c39249ef30ee249e76bff014a903c89372ebd9d755f288656c2dd3ae94f4c020e62a1c16ba24c59fad2461842c417d2cc02cfdfdd0da0700100"
```














