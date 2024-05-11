# Bootcamp Nexa - Fundamentos de IA Generativa e Claude 3

## 📒 Descrição
Com o avanço da IA, atualmente é necessário ter pelo menos um conhecimento na área o que me incentivou a me matricular neste curso para ampliar meus conhecimentos.

## 🤖 Tecnologias Utilizadas
Site do dio e pesquisa nos fóruns e com amigos.

## 🧐 Processo de Criação
Por não ter conhecimento na área dos códigos de IA tive um pouco de dificuldade mas pesquisando e tirando dúvidas com colegas consegui fazer os 3 desafios que estavam na plataforma DIO.

## 🚀 Resultados
- No desafio 01/03 nós tivemos que criar uma função 'encontrar_modelo' para encontrar o modelo correspondente à característica fornecida, e adicionamos os códigos abaixo:

def encontrar_modelo(caracteristica_fornecida):
    for caracteristica, valor in caracteristicas_modelos.items():
        if caracteristica in caracteristica_fornecida.lower():
            return valor
    return "Modelo não encontrado."

- No desafio 02/03 nós tivemos que criar uma função que recebe as características desejadas e recomenda um modelo de IA com base nos dados informados e adicionamos o código abaixo :   
def recomendar_modelo(caracteristicas):
    modelos = [
        ModeloIA("Claude 3 Opus", desempenho=9, velocidade=10, custo=5, capacidades=["pesquisa", "desenvolvimento acelerado"]),
        ModeloIA("Claude 3 Sonnet", desempenho=8, velocidade=5, custo=7, capacidades=["codificação", "recuperação de informações"]),
        ModeloIA("Claude 3 Haiku", desempenho=7, velocidade=9, custo=6, capacidades=["velocidade", "resumo de dados não estruturados"]),
        
    ]

- No desafio 03/03 nós tivemos que criar uma lista de dicionários representando os três modelos do Amazon Bedrock, com 'nome', 'pontuacao_desempenho' e 'preco_mensal' :

modelos_disponiveis = [
    {"nome": "Claude 3 Opus", "pontuacao_desempenho": 9, "preco_mensal": 600},
    {"nome": "Claude 3 Sonnet", "pontuacao_desempenho": 8, "preco_mensal": 450},
    {"nome": "Claude 3 Haiku", "pontuacao_desempenho": 7, "preco_mensal": 350}
  
]

Além de definir melhor a recomendação dos modelos como o nosso trecho do código abaixo:

def recomendar_modelo(modelos, orcamento):
    if orcamento < 250:
        return None, "Seu orçamento é muito baixo para recomendar um modelo adequado."

    modelos_dentro_orcamento = [modelo for modelo in modelos if modelo['preco_mensal'] <= orcamento]

    if not modelos_dentro_orcamento:
        modelo_mais_proximo = min(modelos, key=lambda x: abs(x['preco_mensal'] - orcamento))
        return modelo_mais_proximo['nome'], "Este modelo está mais próximo do seu orçamento."
    else:
        melhor_modelo = max(modelos_dentro_orcamento, key=lambda x: x['pontuacao_desempenho'])
        return melhor_modelo['nome'], "Melhor desempenho dentro do seu orçamento."

## 💭 Reflexão (Opcional)
Foi um desafio mas com pesquisas e estudos consegui finalizar!
