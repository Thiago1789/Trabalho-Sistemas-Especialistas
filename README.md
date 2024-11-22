info_doenca = {
    "Dengue": ["febre alta", "dor de cabeça", "dor atrás dos olhos", "dores musculares", "manchas vermelhas"],
    "Diabetes": ["sede excessiva", "urinar frequentemente", "cansaço", "perda de peso inexplicada", "visão embaçada"],
    "Hipertensão Arterial": ["dor de cabeça", "tontura", "zumbido no ouvido", "cansaço", "visão turva"],
    "Depressão": ["tristeza persistente", "falta de energia", "perda de interesse", "dificuldade para dormir", "falta de concentração"],
}

print("")

print("Bem-vindo ao sistema de diagnóstico inicial!")


print("Digite os seus sintomas separados por vírgula. Exemplo: febre alta, dor de cabeça, tontura e etc ")

paciente = input("Seus sintomas: ").lower()
sintomas_paciente = paciente.split(", ")

resultado = {}

for doenca in info_doenca:
    sintomas = info_doenca[doenca]
    match_count = 0

    for sintoma in sintomas_paciente:
        if sintoma in sintomas:
            match_count += 1

    porcentagem = (match_count / len(sintomas)) * 100
    resultado[doenca] = porcentagem

print("\nResultados:")
for doenca in resultado:
    print(f"{doenca}: {resultado[doenca]:.1f}% de chance.")
