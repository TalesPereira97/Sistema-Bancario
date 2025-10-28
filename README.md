usuario_cadastrado = "admin"
senha_cadastrada = "1234"

tentativas= 0
logado = False 

print("===Banco Python===")

while tentativas < 3:
    usuario = input("Digite seu usuário:")
    senha = input("Digite sua senha:")
    if usuario == usuario_cadastrado and senha ==senha_cadastrada:
        print("Login realizado com sucesso!")
        logado = True
        break
    else:
        tentativas += 1
        print(f"Usuário ou senha incorretos! Tentativa {tentativas}/3")
if not logado:
        print("Número máximo de tentativas atingido. Encerrando o programa.")
        exit()

saldo = 0.0
limite_diario = 1000.0
saque_diario =0.0
total_depositado =0.0
total_sacado =0.0
qtd_operacoes = 0.0
while True:
    print("\n===BANCO PYTHON===")
    print("1- Ver saldo")
    print("2-Depositar")
    print("3- Sacar")
    print("4- Resumo da conta")
    print("5- Sair")
    opcao=input("Escolha uma opção:")

    if opcao== "1":
        print(f"Seu saldo é: R${saldo:.2f}" )

    elif opcao== "2":
        deposito = float(input("Digite o valor do depósito:R$"))
        if deposito > 0:
            saldo += deposito
            total_depositado += deposito
            qtd_operacoes += 1
            print(f"Depósito realizado! Novo saldo: R${saldo:.2f}")
        else:
            print("Valor inválido! Informe um valor positivo.")

    elif opcao == "3":
        saque = float(input("Digite o valor do saque:R$"))
        if saque > 0:
            if saque <= saldo:
                saldo -= saque
                total_sacado += saque
                qtd_operacoes += 1
                print(f"Saque realizado! Novo saldo: R$ {saldo:.2f}")
            else:
                print("Saldo insuficiente!")
        else:
            print("Valor inválido! Informe um valao positivo")

    elif opcao == "4":
        print("\n=== Resumo da Conata ===")
        print(f"Saldo atual: R${saldo:.2f}")
        print(f"Total depositado: R${total_depositado:.2f}")
        print(f"Totala sacado: R${total_sacado:.2f}")
        print(f"Quantedade de operações realizadas:{qtd_operacoes}")
    elif opcao == "5":
        print("Obrigado por usar o Banco Pytho. Até logo!")
        break
    else:
        print("Opção inválida! Escolha novamente.")