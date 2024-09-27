# Dockerfile - Vote (Flask)
FROM python

WORKDIR /app

# Copier et installer les dépendances
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copier le code de l'application
COPY . .

EXPOSE 5000:80

# Lancer l'application avec Gunicorn
CMD ["gunicorn", "<module_name>:<instance_name>", "-b", "0.0.0.0:80", "--log-file", "-", "--access-logfile", "-", "--workers", "4", "--keep-alive", "0"]
