FROM python:3.9-alpine
WORKDIR /app

RUN apk update

COPY requirements.txt .
RUN pip install -r requirements.txt

COPY . .

RUN adduser -D nonrootuser
USER nonrootuser
EXPOSE 5000
CMD ["gunicorn", "--bind", "0.0.0.0:5000", "app:app"]
