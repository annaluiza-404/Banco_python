# Banco_python

saldo=0
deposito=0
saldo_atual=[]
while True:
    print('MENU\n1-Depositar\n2-Sacar\n3-Extrato\n4-Sair')
    op=int(input('Digite a opção:'))
    if op==4:
        break
    elif op==1:
        deposito=float(input('Digite a quantia de dinheiro que deseja depositar:R$'))
        if deposito<0:
            print('Não é possível depositar um valor negativo!')
        else:
             saldo+=deposito
    elif op==2:
        for c in range(0,3):
            saque=float(input('Digite a quantia que deseja sacar:R$'))
            if saque>500:
                print('Você não pode sacar mais de R$500,00 por vez!')
            elif saque>saldo:
                print('Você não pode sacar por falta de saldo!')
                break
            else:
                saldo=saldo-saque
                saldo_atual.append(saque)
    elif op==3:
        print('Seu extrato bancário:\n')
        print(f'Seus depósitos:R${deposito:.2f}\n')
        if not saldo_atual:
            print('Nenhum saque realizado')
        else:
            for saque in saldo_atual:
                print(f'Seus saques:R${saque:.2f}')
        print(f'Seu extrato bancário atual:R${saldo:.2f}\n')
