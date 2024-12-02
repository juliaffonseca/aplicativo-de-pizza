# aplicativo-de-pizza
sistema criado para realizar pedido de pizza
# Bem-vindo à Pizzaria do Bruno Kostiuk
print("Bem-vindos a Pizzaria do Bruno Kostiuk")

# Menu de opções
def mostrar_menu():
    print("\n*** MENU ***")
    print("Sabores disponíveis:")
    print("PS - Pizza Salgada")
    print("PD - Pizza Doce")
    print("\nTamanhos disponíveis:")
    print("P - Pequena")
    print("M - Média")
    print("G - Grande")
    print("\nPreços:")
    print("Tamanho P - PS: R$30, PD: R$34")
    print("Tamanho M - PS: R$45, PD: R$48")
    print("Tamanho G - PS: R$60, PD: R$66")
    print("***********************")

# Função para capturar o pedido
def capturar_pedido():
    # Lista de sabores e tamanhos válidos
    sabores_validos = ["PS", "PD"]
    tamanhos_validos = ["P", "M", "G"]

    # Verificando sabor
    while True:
        sabor = input("Escolha o sabor (PS para Salgada, PD para Doce): ").upper()
        if sabor not in sabores_validos:
            print("Sabor inválido. Tente novamente.")
            continue
        break

    # Verificando tamanho
    while True:
        tamanho = input("Escolha o tamanho (P para Pequena, M para Média, G para Grande): ").upper()
        if tamanho not in tamanhos_validos:
            print("Tamanho inválido. Tente novamente.")
            continue
        break

    # Retornando o pedido escolhido
    return sabor, tamanho

# Função para calcular o preço com base no sabor e tamanho
def calcular_preco(sabor, tamanho):
    # Modelo aninhado de if/else para calcular o preço
    if sabor == "PS":
        if tamanho == "P":
            return 30
        elif tamanho == "M":
            return 45
        elif tamanho == "G":
            return 60
    elif sabor == "PD":
        if tamanho == "P":
            return 34
        elif tamanho == "M":
            return 48
        elif tamanho == "G":
            return 66

# Função principal para executar o pedido
def fazer_pedido():
    total = 0  # Acumulador para o valor total do pedido

    while True:
        # Exibir menu ao cliente
        mostrar_menu()

        # Capturar o pedido
        sabor, tamanho = capturar_pedido()

        # Calcular o preço do pedido
        preco = calcular_preco(sabor, tamanho)
        total += preco

        print(f"Você pediu uma pizza {sabor} de tamanho {tamanho}. Valor: R${preco}")

        # Perguntar se deseja fazer mais pedidos
        mais_pedido = input("Deseja pedir mais alguma coisa? (S/N): ").upper()
        if mais_pedido == "N":
            print(f"Total do pedido: R${total}")
            break

# Executando o programa
fazer_pedido()

