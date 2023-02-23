FROM python:3.8.10

RUN mkdir -p /home/project/app

WORKDIR /home/project/app

COPY requirements.txt /home/project/app

RUN pip install --upgrade pip 
#&& \ pip install --no-cache-dir -r requirements.txt

RUN pip install --no-cache-dir -r requirements.txt

COPY . /home/project/app

ENV TZ=Africa/Nairobi
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

CMD ["uvicorn", "src.app:app", "--reload", "--port", "8000", "--host", "0.0.0.0"]