# brado
<a href="https://crates.io/crates/brado">
  <img src="https://img.shields.io/crates/v/brado.svg" alt="latest release" />
</a>
<a href="https://crates.io/crates/brado">
  <img src="https://img.shields.io/crates/d/brado" alt="latest release" />
</a>
</a>
<a href="https://github.com/brenomfviana/brado/issues">
  <img src="https://img.shields.io/github/issues/brenomfviana/brado" alt="latest release" />
</a>

Brado (BRAzilian DOcs validator) é um pacote Rust para validação de documentos brasileiros.

Este projeto é inspirado no [validate-docbr](https://github.com/alvarofpp/validate-docbr).

Para adicionar o pacote ao projeto:

```bash
cargo add brado
```

A documentação pode ser acessada [aqui](https://docs.rs/brado/) (ainda em desenvolvimento).


## Testes

Para rodar os testes, basta executar o comando a seguir:

```
make test
```

## Documentos

- [x] CPF: Cadastro de Pessoas Físicas;
- [x] CNH: Carteira Nacional de Habilitação;
- [x] CNPJ: Cadastro Nacional da Pessoa Jurídica;
- [ ] CNS: Cartão Nacional de Saúde;
- [ ] PIS: PIS/NIS/PASEP/NIT;
- [ ] Título eleitoral: Cadastro que permite cidadãos brasileiros votar;
- [ ] RENAVAM: Registro Nacional de Veículos Automotores;
- [ ] Certidão de Nascimento/Casamento/Óbito.


## Funções

Todos os documentos possuem as mesmas funções e funcionam da mesma forma.

### validate

```rust
use brado::cpf;
cpf::validate("639.292.470-11"); // true
cpf::validate("639.292.470-10"); // false
```

### mask

```rust
use brado::cpf;
cpf::mask("63929247011"); // "639.292.470-11"
```

### generate

```rust
use brado::cpf;
cpf::generate(); // "63929247011"
cpf::generate_masked(); // "639.292.470-11"
```


# Como Contribuir

1. Instalar nix (com flakes, ou seja, >2.4);
2. Fazer um fork do projeto;
3. Clonando o repositório, e considerando que se está usando `direnv`:
```bash
nix flake clone github:your-github-user/brado --dest ./brado \
&& cd brado 1>/dev/null 2>/dev/null \
&& direnv allow
```
