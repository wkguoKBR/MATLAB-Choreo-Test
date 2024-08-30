# Dockerfile for image: bondtools
# 
# Sample docker build command:
# wsl docker build -f "Dockerfile" -t bondtools "."

# FROM matlabruntime/r2024a/release/update4/108000000000000000
FROM wkguo/matlabruntime:latest

COPY ./applicationFilesForMATLABCompiler /usr/bin/mlrtapp
RUN chmod -R a+rX /usr/bin/mlrtapp/*

RUN if ["$(getent passwd appuser | cut -d: -f1)" = ""] ; then useradd -ms /bin/bash appuser ; fi
USER appuser

ENTRYPOINT ["/opt/matlabruntime/R2024a/bin/glnxa64/muserve", "-a", "/usr/bin/mlrtapp/bondtools.ctf"]
