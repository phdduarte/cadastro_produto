# O projeto
Feito em Angular 9 para aprendizado e retirado do curso  para cadastro de produtos.
Projeto feito para o aprendizado em Angular retirado do curso do Leonardo Leitão e [disponível gratuitamente no YouTube](https://www.youtube.com/playlist?list=PLdPPE0hUkt0rPyAkdhHIIquKbwrGUkvw3).
É um CRUD de produtos.

# Backend simples feito em JSON Server
O foco aqui é desenvolver a parte de Angular por isso não tivemos foco na parte do backend.
A api foi feita utilizando [JSON server](https://www.npmjs.com/package/json-server) uma forma fácil de criar um bd utilizando JSON. Para ver como foi feito acesse a pasta backend.

# FrontEnd

# Árvore de Componentes
![Árvore de Componentes](img_readme/arvore.png)

# Inicialização da APP
![Inicialização da APP](img_readme/initial.png)

## Diferença no Angular - Modulo
- Diferente de outros framework JS o angular possui mas uma camada que é
os Modulos os quais podem armazenar dentro deles os componentes. 
E esses componentes dentro dos modulos só podem ser vistos no seu modulo.

# O que é um Componente?
![Inicialização da APP](img_readme/component.png)

## Estrutura de um Componente Angular
- Componente Angular deve ser formado por três elementos,
template (HTML), estilo (CSS) e classe (TypeScript). 
Essas partes são organizadas em arquivos separados e unidas nos metadados 
do componente através do decorator @Component.

# Organização Usando Módulo
![Organização Usando Módulo](img_readme/modulo.png)
- Na imagem apenas o componente H poderia ficar dentro do módulo Y
porque ele é único referenciado dentro do módulo. 
Os outros todos são referenciados por componentes fora do módulo.

## O que são módulos
- No contexto do Angular um módulo é a forma de agrupar 
componentes, diretivas, pipes e serviços que são relacionados.

## Anatomia do Módulo
![Anatomia do Módulo](img_readme/anatomia.png)

## Crindo o projeto

Primeiro instalamos a [CLI do Angular](https://cli.angular.io/). 

```
npm i -g @angular/cli
```

### ng new nome_diretorio

A CLI Angula facilita a criação de um aplicativo que já funciona, pronto para uso.

```
ng new frontend
```

Va para a pasta frontend

```
cd frontend
```

e start o projeto 

```
npm start
```

ele vai abrir no link: http://localhost:4200/

# Attribute Directives (Diretivas de Atributos)

Altera a aparência e o comportamento de um elemento,
componente ou outra diretiva.

```ts
@Directive({
    selector: '[appRed]'
})
export class RedDirective {
    constructor(el: ElementRef) {
        el.nativeElement.style.color = '#e35e6b';
    }
}
```

```html
<i class="material-icons v-middle" appRed>
    favorite
</i>
```

# Structural Directives (Diretivas estruturais)

Altera o layout adicionando e removendo elementos da [DOM](https://tableless.com.br/entendendo-o-dom-document-object-model/).


```html
<form *ngIf="product" class="product-form"></form>
```

```html
<ul>
    <li *ngFor="let product of products">
        {{ product.name }}
    </li>
</ul>
```

# Property Binding (Vinculação de Propriedade)

```html
<table [dataSource]="products"></table>
```

```ts
@Component({
    selector: 'app-product-read',
    templateUrl: './product-read.component.html',
    stylesUrls: ['./product-read.component.css']
})
export class ProductReadComponent {
    implements OnInit {
        products: Product[];
    }
}
```

Time: 15:00 min