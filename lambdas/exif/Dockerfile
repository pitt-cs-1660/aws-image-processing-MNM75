FROM public.ecr.aws/lambda/python:3.13

# install uv
COPY --from=ghcr.io/astral-sh/uv:latest /uv /uvx /bin/

WORKDIR ${LAMBDA_TASK_ROOT}

COPY pyproject.toml ./
RUN uv sync --no-dev
COPY handler.py .
ENV PYTHONPATH="${LAMBDA_TASK_ROOT}/.venv/lib/python3.13/site-packages:${PYTHONPATH}"
CMD ["handler.exif_handler"]
############
#
# TODO: implement the rest of the image
#
############
