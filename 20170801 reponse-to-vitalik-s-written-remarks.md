# 비탈릭의 비평에 대한 회신 (Reponse to Vitalik's Written Remarks)

방금 전 [비탈릭이 레딧에 쓴 게시글 (영문)](https://np.reddit.com/r/ethereum/comments/6qm0y2/is_the_ethereum_team_defending_their_ground/dkyk94c/)을 보았습니다.

비탈릭은 수수료와 투표에 대한 문제제기를 하였습니다. 두 가지 문제 모두 고려할 가치가 있다고 느껴집니다.

## 클라이언트에서의 검증 (client-side validation)

> 마스터 노드들이 정상적으로 동작할 프로토콜 상의 경제적 인센티브가 없으며, 클라이언트에서의 검증 능력이 결여되어 있습니다. 즉, 투표 체제에 극도로 의족하게 됩니다.

우리가 논의를 진행하려면 단어의 정의부터 내려야 합니다. 저는 "클라이언트에서의 검증"이라는 구절을 블록을 생산하지 않는 풀 노드(non-producing full nodes)들의 검증으로 해석하였습니다. 왜냐하면 이 맥락에서 "경량화된 클라이언트 검증(light client validation)"의 뜻으로 해석하기엔 안맞기 때문입니다. EOS, Steem, Bitshares 모두 블록 생산자보다 많은 "블록을 생산하지 않는 풀 노드"를 가지고 있습니다. BTS와 STEEM을 주고받는 것은 ETH보다 빠릅니다. 비탈릭의 의견은 근본적으로 잘못되었습니다.

블록 생산자들은 비정상적인 블록을 만들 권한이 없습니다. 모든 교환 거래는 풀 노드 혹은 부분 노드에서 이루어지므로 트랜잭션과 관련된 부분 집합에 의해 검증됩니다.

이더리움 경량 클라이언트들은 로직이 아닌 해쉬만을 검사하므로 검증을 위해 맹목적으로 블록 생산자를 신뢰해야 합니다. 그러므로 신뢰성이 무너지는 순간은 마이닝 풀의 담합이며, 이는 선출된 블록 생산자들의 담합과 유사합니다. 두 방식의 결정적 차이는 더 많은 선출된 블록 생산자가 있으며, 그들의 권력은 집중화된 마이닝 풀과 비교할 때 더 고르게 분배되었다는 점입니다.

## 투표 참여율 (Voter Turnout)

비탈릭은 이어서 투표에 관한 문제점을 제기합니다.

> 투표 방식은 다음의 문제점을 가지고 있습니다.

> - 낮은 투표 참여율 (DAO carbonvote, 현재 EIP186 carbonvote, DAO 제안 투표, 또한 Bitshares의 2014년 DPOS 투표 모두 10% 미만의 참여율을 보임)
> - 게임 이론, 공유지의 비극 취약점 : 한명의 투표자는 결과에 대해 아주 미미한 영향력만 행사할 수 있으므로, 합리적으로 투표할때 얻는 가치는 사회 최적 가치에 비해 수천배 낮습니다. 사용자들이 그들의 코인을 거래소에 예치하고, 거래소가 사용자를 대신해 투표를 하는 상황에서, 사용자들의 돈을 가지고 거래소가 어떻게 투표하는지 신경도 안쓰는 결과가 발생할 수 있습니다.
> - 코인 보유자들의 관심사는 일반 사용자들의 관심사와 완벽히 일치하지 않습니다. 그러므로 시스템의 개선이 아닌 코인의 가격만 올리는 방향으로 흘러갈 수 있습니다.

지난 3년간 낮은 투표 참여율을 개선하기 위해 프록시 투표, 보다 간편한 사용자 인터페이스, 투표를 하기 위한 절차의 감소가 이루어졌습니다. 투표 참여자들은 평균적으로 20% 이상의 토큰 보유량 상승을 보였습니다. "거래소 투표"에 대한 우려는 스팀 파워(거래소가 유동 화폐를 보유해야 함)로 크게 개선되었으며, 약관으로 완전히 개선할 수 있습니다.

더 나아가, 비 유권자는 보안성을 약화시키지 않습니다. 그들은 토큰을 보유하고 있으며, 공격자들의 지분 획득 비용을 높이는데 일조합니다. 다량의 토큰 보유자(역주:고래)들은 그들의 자산을 보호하며, 시스템의 가장 큰 고래보다 더 많은 자산을 소유하려고 하는 공격자로부터 보호하는 큰 가치를 얻기위해 투표에 참여합니다. Steem과 Bitshares의 투표 참가수와 이더리움의 자산 규모를 대입하였을 때, 공격자는 (구매 압력이 가격을 상승하지 않는다 가정할 때) 수조원의 금액을 지불해야 하며, 공격자들은 문제가 발생하였을 때 쉽게 내보낼 수(forked out) 있습니다.

만약에 공격자들이 거대 고래와 결탁한다면, 고래들은 "공격"이 프로토콜을 향상시킬 기능이라 생각하거나, "커뮤니티"가 고래를 내보낼 것입니다. 비트코인과 이더리움은 모두 큰 영향력을 가진자들이 대다수의 관심사와 반하는 변화를 일으키려고 할 때 어떠한 일(ETC와 BCC)이 일어나는지 보여주었습니다.

## 수수료 (Fees)

마지막으로 비탈릭은 수수료를 언급합니다.

> EOS는 트랜잭션 비용을 청구하는 것이 아닌, 일정 기간 N*k개의 트랜잭션을 전송하기 위해 N개의 토큰을 가지고 있어야 하는 규칙(스팀 백서 참고)을 메카니즘으로 삼습니다. 이는 사용성 측면에서 바람직하지 않은 결과를 낳습니다. 사용자들은 N개의 토큰을 구매해야만 하며, 변동성에 노출되어야 합니다. 다음과 같은 상황에서 문제가 됩니다.

> - 빈곤층 : 블록체인을 사용하기 위해 힘들게 저축한 돈을 겉이 번지르르한 신상 가상화폐에 집어넣을 생각이 없는 사람.
> - 블록체인을 몇번 쓰고 떠날사람 (코인을 사고 팔아야 됨)
> - 이더리움 역시 후자는 마찬가지이나, 그들은 수수료만 내면 되므로 구매량은 크지 않을겁니다. 이를 위해 몇달러 어치 이더를 더 구매하는건 큰 일은 아닙니다.

저 역시 빈곤층의 경우 플랫폼을 사용하기 위해 어떠한 가상 화폐를 구매해선 안된다고 생각하며, 그렇기 때문에 수수료가 문제가 되는겁니다. 이더리움으로 스팀을 구현하면 수수료로 모든 사용자를 내칠 수 있을겁니다. 모든 암호화폐는 극소량을 구매하려고 해도 고정 비용이 발생합니다. 계정을 만들어야 되고, 은행 송금 수수료를 내야되고, 개인 신분 증명을 해야되고, 거래소 수수료를 내는 등의 비용을 말이죠. 이러한 과정을 처음으로 수행할 때 소요되는 시간과 비용을 정당화하려면 10만원어치의 가상화폐를 구매해야 합니다. 이러한 과정의 비용이 10원의 수수료처럼 될거라고는 절대 생각되지 않습니다.

> - 갑작스런 방문자 수 증가를 겪은 사람 (예: 아마도 여러분) : 사용자들은 99%의 예상 방문량을 소화할 수 있는 충분한 양의 코인을 구매해야 합니다. 그래야만 "가스가 떨어지는" 상황이 발생해 거래소로 달려갈 필요가 없습니다.

블록체인 대역폭 할당의 부분 지급(fractional reserve) 속성으로 인해, 대부분의 사람들은 그들의 "초기 부하"에 해당하는 토큰을 구매하면 되며, 네트워크에서 수요 급증을 처리하게 됩니다. 오직 네트워크가 100% 부하일 경우에만 99%의 사용량에 대한 토큰을 구매하면 됩니다. 그러나 사람들이 99%의 사용량에 대한 토큰을 구매할 여력이 있다면 네트워크는 평균 사용량 기간동안 사용하지 않는 대역폭을 가지고 있을 것이므로 100% 부하는 일어나지 않을 것입니다. 그러므로, 시장이 자동적으로 균형을 맞추고 사람들은 최대 사용량이 아닌 평균 사용량에 맞추어 구매할 것으로 결론을 낼 수 있습니다.

## 서비스의 비용 지불 (Service Should Pay)

마지막으로 EOS는 서비스 제공자(DApp 개발자)들이 네트워크 비용을 지불하는 아이디어를 바탕으로 설계되었습니다. 사용자들이 아닙니다. 훌륭한 애플리케이션은 네트워크 운영과 완전히 독립적인 수익 모델이 필요합니다.

Steem은 우리가 보여야 할 "비용 없는" 트랜잭션과 사용자들의 지분 필요성에 대한 문제를 어떻게 해결하였는지에 대한 증명입니다.

## 캐스퍼 (Casper)

비탈릭의 투표 모형에 대한 비판은 "처벌 조건의 부재"에서 시작됩니다. 말하자면, 블록 생산자는 잘못을 저질러도 죄를 받지 않는다는 것입니다. 만약에 향후 수익과 명성의 손실을 무시한다면, DPOS는 간단히 동일한 타임스탬프를 만든 생산자를 처벌하여 새로운 포크를 만들 수 있습니다. 블록 생산자들에게 채권을 지게 하여 약관의 객관적이나 주관적 해석에 따라 자본가들이 블록 생산자의 자본을 몰수하게 하는 것도 간단합니다.

저는 [이더리움의 자본증명 알고리즘인 캐스퍼에 대한 리뷰 글 (영문)](http://bytemaster.github.io/2015/08/08/Review-of-Casper-Ethereums-proposed-Proof-of-Stake-Algorithm/)로 알고리즘이 틀렸음을 보여주었습니다.

1. 과도한 알고리즘의 계산 비용이 트랜잭션 처리량에 제한을 일으킴
2. 다음 블록 생산자에게 경제적인 배팅을 하는 것은 경쟁이 아닌 공모와 담합을 유발함
3. 궁극적으로 캐스퍼는 지분에 비례하여 보상을 나누는 거대 주주 연합에 의해 라운드-로빈 방식으로 블록을 생산할 것임

결과적으로, 캐스퍼에서 소규모 생산자들은 블록 생산에 어떠한 영향도 주지 않을 것이며, 블록 당 통신의 네트워크 오버헤드는 굉장히 증가할 것입니다. (낮은 지연시간을 가지는 연결에 유리하며, 점차 중앙화 될 것입니다.)

## 결론

DPOS, EOS, STEEM에 대한 비판은 결함을 가진 경제적 가설, 잘못된 정보, 그들이 제안한 해결책이 가진 취약점에 대한 무지와 무시에서 비롯됩니다. 저는 투표가 이상적이지 않다고 충분히 인지하고 있습니다. 하지만 현재로써 모든 위협, 공격 수단, 복구 방법을 고려할 때 최선의 선택입니다.