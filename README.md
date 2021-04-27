## Clone o repositorio

```bash
git clone https://github.com/carreirorco/flisol-demo.git
cd flisol-demo
```

## Crie uma chave ssh chamada flisol

```bash
ssh-keygen -q -f flisol -P ""
```

## Inicie as maquinas virtuais

```bash
vagrant up
```

## Verifique se as VMs estao respondendo

```bash
ansible servers -m ping
```

## Brinque com os playbooks

```bash
ansible-playbook common.yml
```
