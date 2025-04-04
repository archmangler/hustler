FROM python:3.12-slim

# set the working directory in the container
WORKDIR /app

# copy the requirements file into the container
COPY pyproject.toml poetry.lock* /app/

RUN pip install poetry \
    && poetry install --no-root

# copy the rest of the application code into the container
COPY . /app
RUN poetry install

# set the entrypoint to the asset-processing-service
ENTRYPOINT ["poetry", "run", "asset-processing-service"]


