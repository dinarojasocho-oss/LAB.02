import sqlite3
import pandas as pd

# 1. Conexión al archivo de base de datos SQLite
conn = sqlite3.connect("datos_lab2.db")

# 2. Consulta con filtro WHERE y orden
query = """
SELECT nombre, ciudad, fecha_registro
FROM clientes
WHERE ciudad = 'Lima'
ORDER BY fecha_registro DESC
LIMIT 10;
"""

# 3. Ejecuta la consulta y la trae como DataFrame
df = pd.read_sql_query(query, conn)

print(df)

conn.close()
