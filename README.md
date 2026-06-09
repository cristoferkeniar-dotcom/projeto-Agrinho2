# projeto-Agrinho2
import random
import time

# Função que simula leitura de sensor de umidade do solo
def ler_umidade_solo():
    return random.uniform(10.0, 80.0)  # umidade em percentual

# Função para decidir se a irrigação deve ser acionada
def verificar_irrigacao(umidade, limite=30.0):
    if umidade < limite:
        print(f"Umidade {umidade:.2f}% - Irrigação acionada!")
        return True
    else:
        print(f"Umidade {umidade:.2f}% - Solo adequado, irrigação desligada.")
        return False

# Loop de monitoramento
while True:
    umidade_atual = ler_umidade_solo()
    verificar_irrigacao(umidade_atual)
    time.sleep(5)  # aguarda 5 segundos para próxima leitura
