# How to use Container
```bash
# docker run
# -v: set volume mount
# -w: set workdir


# alias ansible="docker run \
#   -it --rm \
#   -v ~/.ssh:/root/.ssh \
#   -v ~/.aws:/root/.aws \
#   -v $(pwd):/apps \
#   -w /apps \
#   alpine/ansible ansible"

# ansible <follow command>


alias ansible-playbook="docker run \
  -it --rm \
  -v ~/.ssh:/root/.ssh \
  -v ~/.aws:/root/.aws \
  -v $(pwd):/apps \
  -w /apps alpine/ansible \
  ansible-playbook"

ansible-playbook -i env_stg playbook.yml
ansible-playbook -i env_prd playbook.yml
```