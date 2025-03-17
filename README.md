def calcular_promedio_temperatura(temperaturas):
    """
    Calcula el promedio de temperatura para cada ciudad en un período de tiempo.

    Parámetros:
    temperaturas (dict): Diccionario donde las claves son los nombres de las ciudades
                         y los valores son listas de temperaturas semanales.

    Retorna:
    dict: Diccionario con los promedios de temperatura por ciudad.
    """
    promedios = {}

    for ciudad, temp_list in temperaturas.items():
        if len(temp_list) > 0:
            promedio = sum(temp_list) / len(temp_list)  # Calcula el promedio
            promedios[ciudad] = round(promedio, 2)  # Redondea a 2 decimales
        else:
            promedios[ciudad] = None  # Manejo de error si una ciudad no tiene datos

    return promedios


# Datos de ejemplo: Temperaturas registradas en 3 ciudades durante 4 semanas
temperaturas_ciudades = {
    "Ciudad A": [20, 22, 21, 19],
    "Ciudad B": [25, 26, 24, 27],
    "Ciudad C": [18, 17, 19, 16]
}

# Llamada a la función y visualización de resultados
resultados = calcular_promedio_temperatura(temperaturas_ciudades)

# Mostrar resultados en consola
for ciudad, promedio in resultados.items():
    print(f"La temperatura promedio en {ciudad} es {promedio}°C.")
