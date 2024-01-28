<pre>
#!/bin/bash
  
WORKING_DIR="/data"
IMAGE_NAME="rosetta-relax:3.12"

mkdir output

for pdb_file in *.pdb; do
  docker run -v "$(pwd)":${WORKING_DIR} -w ${WORKING_DIR} -it ${IMAGE_NAME} ${WORKING_DIR}/${pdb_file} 2
  mv *01.pdb output/
done
</pre>
