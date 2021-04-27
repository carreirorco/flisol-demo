## Clone o repositorio

```bash
git clone https://github.com/carreirorco/flisol-demo.git
cd flisol-demo
```

## Crie uma chave ssh chamada flisol

```bash
ssh-keygen -q -f flisol -N ""
chmod 400 flisol flisol.pub
```

## Inicie as maquinas virtuais

```bash
vagrant up
```


