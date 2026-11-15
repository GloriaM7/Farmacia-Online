# Requisitos, backlog e testes da Farmácia Online

A [página inicial do projeto](README.md) reúne os seis PDFs e os links para Figma, GitHub Projects e Google Sheets.

## Rastreabilidade funcional

Os códigos RF e UC seguem a [Etapa 1](Etapa01RequisitoseUmlABNTGTI.pdf). Na [Etapa 6](Etapa06TesteABNTGTI.pdf), CT01 a CT23 identificam os casos da planilha. A tabela indica os cenários planejados associados a cada item do backlog.

| Product Backlog | Requisito | Caso de uso | Casos de teste planejados |
| --- | --- | --- | --- |
| [PB01 · Cadastro e login](https://github.com/GloriaM7/Farmacia-Online/issues/2) | RF01 | UC01 | CT01–CT02, CT21 |
| [PB02 · Catálogo e pesquisa](https://github.com/GloriaM7/Farmacia-Online/issues/3) | RF02 | UC02 | CT03–CT04, CT22 |
| [PB03 · Detalhes dos medicamentos](https://github.com/GloriaM7/Farmacia-Online/issues/4) | RF02 | UC02 | CT05–CT06 |
| [PB04 · Envio de receitas](https://github.com/GloriaM7/Farmacia-Online/issues/5) | RF03 | UC03 | CT07–CT08 |
| [PB05 · Análise farmacêutica](https://github.com/GloriaM7/Farmacia-Online/issues/6) | RF07 | UC04 | CT09–CT10 |
| [PB06 · Carrinho e frete](https://github.com/GloriaM7/Farmacia-Online/issues/7) | RF04 | UC05 | CT11–CT12, CT23 |
| [PB07 · Pagamento](https://github.com/GloriaM7/Farmacia-Online/issues/8) | RF05 | UC06 | CT13–CT14 |
| [PB08 · Acompanhamento dos pedidos](https://github.com/GloriaM7/Farmacia-Online/issues/9) | RF06 | UC08–UC09 | CT15–CT16 |
| [PB09 · Produtos e estoque](https://github.com/GloriaM7/Farmacia-Online/issues/10) | RF08 | UC07 | CT17–CT18 |
| [PB10 · Gerenciamento das entregas](https://github.com/GloriaM7/Farmacia-Online/issues/11) | RF09 | UC09 | CT19–CT20 |

Quando um item exige receita, o cliente envia o documento após entrar na conta. A finalização da compra fica bloqueada até a aprovação farmacêutica. Pix e boleto permanecem aguardando confirmação. Se o gateway confirmar a recusa, o pedido é cancelado. Depois do pagamento aprovado e da separação, o entregador registra a saída e a conclusão da entrega.

## Sprint 01

A [Etapa 4](Etapa04MetodologiaScrumABNTGTI.pdf) registra a Sprint planejada para duas semanas. A meta foi simular a entrega do acesso à plataforma e da consulta ao catálogo. PB01 (5 SP), PB02 (5 SP) e PB03 (3 SP) passaram por A fazer, Em andamento e Concluído. Os outros sete itens ficaram em A fazer. O gráfico burndown original ilustra oito dias de acompanhamento. Ao baixar os pontos somente na conclusão de cada item, o saldo passa por 13, 8, 3 e 0 pontos após PB01 (dia 2), PB02 (dia 5) e PB03 (dia 8).

## Verificações complementares para homologação

| Requisito | Verificação planejada | Critério |
| --- | --- | --- |
| RNF01 · Proteção de dados | Em homologação, usar contas e receitas fictícias. Verificar se um cliente consegue abrir uma receita ou pedido de outra conta e se perfis sem permissão conseguem analisar receitas. | Negar o acesso fora das permissões previstas. CT16 cobre parte desse cenário para pedidos. |
| RNF02 · Desempenho das buscas | Medir o tempo entre o envio da pesquisa e a exibição dos resultados por nome, categoria e princípio ativo. Registrar a carga e o tamanho do catálogo. | A busca deve responder em até dois segundos nas condições de teste documentadas. |
| RNF03 · Disponibilidade | Monitorar o serviço continuamente durante a janela mensal definida para homologação e registrar as indisponibilidades. | Disponibilidade de pelo menos 99,9% na janela medida. |
| RNF04 · Segurança do pagamento | Verificar em sandbox se a integração com o gateway usa TLS e rejeita uma tentativa com certificado inválido. | Toda comunicação com o gateway usa TLS e a validação do certificado é obrigatória. |
| Usabilidade · Etapa 2 | Percorrer busca, carrinho, envio de receita e acompanhamento em desktop e mobile. Conferir mensagens de erro, retorno às telas e indicação do status. | É possível completar os fluxos, entender as mensagens e recuperar-se de erros de entrada nas duas plataformas. |

Os casos da planilha e as verificações acima aguardam a implementação e o ambiente de homologação.
