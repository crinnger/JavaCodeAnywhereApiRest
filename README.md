# JavaCodeAnywhereApiRest
Projeto gerenciamento de pessoas em API REST

### FEATURES
    -   Cadastro de Pessoa com lista de telefone
        -   Relacionamento Bidirecional entre Person(Lista de Phone) e Phone(Parent Person) 
        -   Necessario uso @JsonManagedReference/@JsonBackReference para que no recebimento do JSON o mapeamento ja instanticar em PhoneDto o campo personDto
        -   Necessario na Entity Person criar um metodo @PostPersist para atualizar a referencia do novo Person criado na Lista de Phone, para que na hora de salvar o Phone 
            o person_id nao ficar NULL
        -   Necessario para o MAPSTRUCK criar no PersonMapper o metedo @AfterMapping para atualizar a referencia de Person na Lista de Phone. 
        -   LOMBOK nao usar @Builder devido necessidade de usar o @AfterMapping do MAPSTRUCK.
        -   Retirar da entidade Phone o ToString e EqualsHashCode do campo personID, Dto e Entity
        
