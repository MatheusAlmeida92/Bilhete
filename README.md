while True:
    print("SIMULADOR DE VALE-TRANSPORTE (VT)")
    print("1 - Simular")
    print("2 - Resumo")
    print("3 - Encerrar")
    escolha = input("Escolha uma opção: ")

    if escolha == '1' or escolha == 'simular':
        salario = float(input("Digite o salário: R$ "))
        dias = int(input("Dias trabalhados (1 a 26): "))
        conducoes = int(input("Conduções por dia (1 a 8): "))
        print("1 - Ônibus (R$ 5,00)\n2 - Metrô/Trem (R$ 5,40)\n3 - Integração (R$ 8,90)")
        tipo = input("Escolha o transporte: ")
        
        tarifa = 5.00 if tipo == "1" else (5.40 if tipo == "2" else 8.90)
        gasto_mes = tarifa * conducoes * dias
        desconto_vt = salario * 0.06
        economia = gasto_mes - desconto_vt

        if gasto_mes > desconto_vt:
            print(f"Vale a pena pedir! Economia de R$ {economia:.2f}")
        elif gasto_mes == desconto_vt:
            print("Tanto faz (custo igual ao desconto).")
        else:
            print("Não compensa pedir o VT.")
            
        if gasto_mes > (salario * 0.10) and dias >= 20:
            print("ALERTA: Gasto > 10% do salário com 20+ dias trabalhados!")

    elif escolha == '2' or escolha == 'resumo':
        print("Módulo de resumo (implementar conforme simulações).")
    elif escolha == '3' or escolha == 'encerrar':
        print("Encerrando o simulador...")
        break
    else:
        print("Opção inválida! Tente novamente.")
