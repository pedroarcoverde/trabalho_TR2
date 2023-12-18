# Trabalho Teleinformática e Redes 2
## Simulador simples de uma comunicação cliente servidor

O código implementa o protocolo RDT com o algoritmo Go-back-N (RDT 4). Esse algoritmo é uma melhoria do RDT básico, pois permite a detecção e correção de erros, além de garantir a entrega ordenada dos pacotes.

A função `rdt_4_0_send` no arquivo rdt.py é responsável pela transmissão dos pacotes. Ela envia os pacotes na janela, que é um conjunto de pacotes que ainda não receberam ACK. Se um pacote for corrompido, o remetente solicitará sua retransmissão. Se o remetente receber um ACK, ele incrementará o número de sequência e removerá o pacote da janela.

A função `rdt_4_cki_receive` no arquivo rdt.py é responsável pela recepção dos pacotes. Se o pacote for corrompido, o destinatário solicitará sua retransmissão. Se o destinatário receber um ACK, ele incrementará o número de sequência e removerá o pacote da janela.

As modificações nos arquivos client.py e server.py são necessárias para usar a nova função `rdt_4_0_send` e `rdt_4_0_receive` em vez das funções básicas de RDT.

Esse novo código é melhor que o antigo, pois garante a entrega ordenada dos pacotes e a detecção e correção de erros, mesmo em situações adversas, como perda de pacotes ou corrupção de dados. Isso é especialmente importante em aplicações críticas, onde a perda de dados pode ter consequências negativas.
