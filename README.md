# time-medicamentos---python

App de lembretes de rotinas de medicametos - codigos em python 

import datetime

medicamento = "Aspirina"
horario = "08:00:00"
rotina = "antes do café da manhã"

# Verifica se o horário atual corresponde ao horário de tomar o medicamento
agora = datetime.datetime.now().strftime("%H:%M:%S")
if agora == horario:
    # Cria uma mensagem personalizada para lembrar o usuário sobre o medicamento
    mensagem = f"Lembre-se de tomar {medicamento} {rotina}. É hora de tomar o medicamento agora!"
    print(mensagem)
else:
    print("Ainda não é hora de tomar o medicamento.")

import datetime
import time
import winsound

# Cria um dicionário vazio para armazenar as informações dos medicamentos
medicamentos = {}

# Solicita ao usuário que informe as informações dos medicamentos
while True:
    nome = input("Informe o nome do medicamento, ou digite 'fim' para finalizar: ")
    if nome == "fim":
        break
    else:
        horario = input("Informe o horário para tomar o medicamento (no formato hh:mm:ss): ")
        rotina = input("Informe a rotina diária (por exemplo, 'antes do café da manhã', 'depois do almoço', 'antes de dormir'): ")
        medicamentos[nome] = {"horario": horario, "rotina": rotina}

# Loop infinito para verificar se o horário atual corresponde a algum horário de medicamento
while True:
    agora = datetime.datetime.now().strftime("%H:%M:%S")
    for nome, info in medicamentos.items():
        if agora == info["horario"]:
            # Toca um som para alertar sobre o horário do medicamento
            winsound.Beep(440, 1000)  # Frequência de 440 Hz por 1 segundo
            print(f"{nome}: Hora de tomar o medicamento ({info['rotina']})")
            # Espera 1 minuto antes de verificar novamente o horário
            time.sleep(60)
    # Espera 10 segundos antes de verificar novamente o horário
    time.sleep(10)


# Diversas rotinas 

import datetime
import time
import winsound

# Cria um dicionário vazio para armazenar as informações das rotinas
rotinas = {}

# Solicita ao usuário que informe as informações das rotinas
while True:
    tipo = input("Informe o tipo de rotina (medicamento, banho, exercício), ou digite 'fim' para finalizar: ")
    if tipo == "fim":
        break
    else:
        horario = input("Informe o horário para a rotina (no formato hh:mm:ss): ")
        rotinas[tipo] = {"horario": horario}

# Loop infinito para verificar se o horário atual corresponde a algum horário de rotina
while True:
    agora = datetime.datetime.now().strftime("%H:%M:%S")
    for tipo, info in rotinas.items():
        if agora == info["horario"]:
            # Toca um som para alertar sobre a rotina
            winsound.Beep(440, 1000)  # Frequência de 440 Hz por 1 segundo
            print(f"Lembre-se de fazer {tipo} agora!")
            # Espera 1 minuto antes de verificar novamente o horário
            time.sleep(60)
    # Espera 10 segundos antes de verificar novamente o horário
    time.sleep(10)
