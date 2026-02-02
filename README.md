import sqlite3
import io
conn = sqlite3.connect(&#39;mydatabase.db&#39;)
with io.open(&#39;clientes_dump.sql&#39;, &#39;w&#39;) as f:
for linha in conn.iterdump():
f.write(&#39;%s\n&#39; % linha)
print(&#39;Backup performed successfully.&#39;)
print(&#39;Saved as mydatabase_dump.sql&#39;)
conn.close()

Output:
Backup performed successfully.
Saved as mydatabase_dump.sql
