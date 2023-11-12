def main():
    # Leitura do tamanho do mapa
    n, m = [int(i) for i in input().split()]

    # Leitura do mapa
    mapa = [list(map(int, input().split())) for _ in range(n)]

    # Leitura da quantidade de personagens
    q = int(input())

    resultados = []

    for _ in range(q):
        # Leitura da posição inicial e movimentos do personagem
        linha, coluna = [int(j) for j in input().split()]
        movimentos = input().strip()

        # Inicialização de variáveis para o personagem
        tesouro_atual = 0

        for movimento in movimentos:
            if movimento == 'N' and linha > 0:
                linha -= 1
            elif movimento == 'S' and linha < n - 1:
                linha += 1
            elif movimento == 'O' and coluna > 0:
                coluna -= 1
            elif movimento == 'L' and coluna < m - 1:
                coluna += 1

            # Atualiza o tesouro atual se encontrar um tesouro na nova posição
            tesouro_atual = max(tesouro_atual, mapa[linha][coluna])

        # Adiciona o resultado à lista de resultados
        resultados.append(f"Caçador {_ + 1}: {tesouro_atual}")

    # Imprime todos os resultados de uma só vez
    for resultado in resultados:
        print(resultado)

if __name__ == "__main__":
    main()

