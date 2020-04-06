FROM openvino:latest

#Install needed dependences
RUN apt-get update && apt-get -y upgrade && apt-get autoremove -y
RUN apt-get install -y --no-install-recommends \
        python3-yaml \
        vim

COPY . /app/

## Download needed models
RUN /opt/intel/openvino/deployment_tools/open_model_zoo/tools/downloader/downloader.py --name person-detection-retail-0013 --output_dir /app/models
RUN /opt/intel/openvino/deployment_tools/open_model_zoo/tools/downloader/downloader.py --name person-reidentification-retail-0031 --output_dir /app/models

# Build Open Model Zoo demos
RUN /opt/intel/openvino/deployment_tools/open_model_zoo/demos/build_demos.sh


CMD ["bash"]
