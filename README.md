# Digitalización de Clientes

## 🧠 Contexto del proyecto

Actualmente, muchos clientes aún realizan pedidos por teléfono o a través de vendedores.  
El objetivo de este proyecto es **identificar qué clientes tienen mayor probabilidad de que su próximo pedido sea digital**, para enfocar los esfuerzos comerciales y de comunicación hacia ellos.

---

## 📊 Datos disponibles

El dataset combina información **a nivel cliente** y **a nivel pedido**.

### Variables de cliente (estáticas)
- Agencia  
- Ruta  
- País  
- Región comercial  
- Tipo de cliente (tienda, minimarket, mayorista)  
- Madurez digital  
- Estrellas  
- Frecuencia de visitas  

### Variables de pedido (dinámicas)
- Canal  
- Monto facturado  
- Materiales distintos  
- Cajas físicas  

**Nota:** Los clientes son multicanal, y el promedio de pedidos digitales ronda el 50%.

---

## 🧩 Planteamiento del problema

Se exploraron dos enfoques:

### 1. Predicción del siguiente pedido
Determinar si el **próximo pedido** del cliente será digital o no.

**Resultado:**  
El modelo no logró buenos resultados debido a que las variables a nivel pedido no aportaban información relevante.  
Las variables más influyentes fueron:
- Madurez digital  
- Porcentaje histórico de pedidos digitales del cliente

**Conclusión:**  
El problema se entiende mejor como un análisis de **potencial digital** del cliente, más que como una predicción puntual.

---

## 🔍 Análisis de potencial digital y clusterización

Se realizó una **segmentación de clientes** usando tres variables:

1. Madurez digital  
2. Porcentaje de pedidos digitales (en los últimos 12 pedidos)  
3. Tendencia de pedidos digitales (creciente o decreciente)

### Clústeres obtenidos

| Clúster | % Pedidos digitales | Madurez digital | Tendencia | Clientes | Descripción |
|----------|----------------------|------------------|------------|------------|--------------|
| Digitales consolidados | 78% | Alta | Variada | 17,201 (13.5%) | Clientes maduros y consolidados en digital |
| En transición digital | 60% | Media | Más digital | 37,593 (30%) | Clientes en crecimiento digital |
| En retroceso | 56% | Media | Menos digital | 26,468 (21%) | Clientes con retroceso digital |
| En desarrollo | 30% | Baja | Más digital | 23,349 (18.5%) | Clientes con alto potencial |
| Rezagados digitales | 35% | Baja | Menos digital | 21,038 (17%) | Clientes con baja madurez y bajo uso digital |

---

## 🧮 Estructura del repositorio

| Archivo | Descripción |
|----------|--------------|
| `Procesamiento transaccional clientes.ipynb` | Limpieza, integración y preparación de datos de clientes y pedidos. |
| `Modelo siguiente pedido.ipynb` | Desarrollo del modelo predictivo de probabilidad de pedido digital (siguiente pedido). |
| `Modelo digitalidad del cliente.ipynb` | Segmentación mediante clusterización y análisis de madurez digital. |

---

## 📈 Conclusiones principales

1. La **madurez digital** del cliente es la variable más explicativa del comportamiento digital.  
2. El **modelo predictivo** no añade valor significativo frente a un análisis descriptivo basado en madurez y proporción digital.  
3. La **clusterización** permite identificar grupos con potencial de digitalización.  
4. El enfoque debe centrarse en **accesibilidad y adopción de la plataforma digital** por parte de clientes con madurez baja y media.

---

## 🚀 Próximos pasos

1. Investigar por qué los clientes alternan entre canales.  
2. Mejorar la accesibilidad y experiencia de la plataforma digital.  
3. Poner en producción el modelo de clusterización y monitorear la evolución de los grupos.  
