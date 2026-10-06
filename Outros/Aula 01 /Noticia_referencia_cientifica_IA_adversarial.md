Notícia: An AI Agent Swarm Hacked 395 PaperCut Instances
(https://incyber.org/en/article/an-ai-agent-swarm-hacked-395-papercut-instances/)

A matéria é sobre uma campanha de ataque automatizada utilizando agentes de IA maliciosos para explorar uma vulnerabilidade no software PaperCut (software de gerenciamento de impressão) expostos na internet. Como o software opera com privilégios no sistema operacional Windows, uma vez comprometido o atacante obtém controle do sistemas da organização. Os atacantes utilizaram centenas de agentes construídos baseados no Codex e um modelo da DeepSeek, equipados com ferramentas ofensivas. A campanha de ataque comprometeu 11 organizações em 26 segundos, o que é impressionante pela velocidade. Destaca-se também o potencial de automação. Sob a ótica da segurança da plataforma de IA, chama atenção o fato de que modelos os mecanismos de alinhamento de segurança dos LLMs, utilizados na ação ofensiva, não impediram, que os agentes fossem utilizados para ações maliciosas. Adicionalmente, os atacantes instruíram os agentes a não atacar organização em alguns países específicos (Rússia, China, entre outros), porém, conforme relatado, foram registrados ataques contra alvos em alguns desses locais, o que sugere falha de instruction following.

Artigo: Cloak, Honey, Trap: Proactive Defenses Against LLM Agents
(https://www.usenix.org/system/files/usenixsecurity25-ayzenshteyn.pdf)

O trabalho menciona sobre o uso de LLM combinado com o uso de ferramentas de pentest por atores maliciosos para ciberataques.
A lacuna de pesquisa é sobre ausência de defesas contra ataques de agentes baseados em LLMs, o que poderia eventualmente evitar ou desacelerar ataques como o relatado na notícia acima. O trabalho lista sete vulnerabilidades estruturais inerentes a modelos baseados na arquitetura transformes para gerar insigths e técnicas de defesa baseadas em 3 estratégias:
Cloak: oculta ou distorce informação crítica para prevenir o atacante de reconhecer ativos de alto valor.
Honey: utiliza específicos honeypots and honeytokens para atrair A e revelando sua presença ou esgotando recursos.
Trap: explora falhas intrínsecas de LLM para atrasara ou parar o ataque da IA.
Os autores demonstraram a capacidade de atrair os agentes para perto ou longe dos ativos importantes da rede ou deixá-los em loops infinitos causando alucinações. Implantando log falso, o defensor pode desencorajar o agente a ignorar o ativo e até executar código arbitrariamente no ambiente adversário, potencialmente dando um reverse shell para os defensores.

Resposta a comentarios:
 Notícia e Referência Acadêmica sobre IA Adversarial » o ataque do "poema" contra o ChatGPT
 Esse caso me leva a pensar que outros possíveis gatilhos poderiam ser utilizados para exploração do modelo, pois a correção de um gatilho específico pode não eliminar necessariamente a causa do problema. Devido a similaridade de arquitetura, o mesmo cenário talvez se aplica a outros modelos. Concordo também com a importância da transparência e, inclusive, acho que esse tipo de vulnerabilidade deveria ser registrada e estar pública. Embora as empresas divulguem informações sobre os modelos, deveria manter uma atualização constantemente de falhas identificadas (corrigidas ou não) mantendo o histórico dessas vulnerabilidades e medidas adotadas. Acho bem difícil que isso ocorra ...

 Notícia e Referência Acadêmica sobre IA Adversarial » Cliente convence chat da chevrolet a vender carro por 1 dólar.

 A notícia me parece a exploração de vulnerabilidade de supply chain, acho que os riscos tinham que ser melhor avaliados pela empresa previamente a implementação do chatbot. Além dos guardrails, eu retiraria da LLM qualquer autonomia para concluir ou avaliar negócios.
