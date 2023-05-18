## GraphQL 이란?

[A query language for your API](https://graphql.org/)

GraphQL의 공식 문서를 살펴보면

_GraphQL은 API용 쿼리 언어이자 기존 데이터로 이러한 쿼리를 수행하기 위한 런타임입니다._

라고 서술되어 있다.

GraphQL에 대해 알아보려면 먼저 api 의 개념을 짚고 가야 하는데

이미 아시는 분들은 넘어가시길 바란다.

**먼저 api란?**

Application Programming Interface 의 약자로

쉽게 말하자면 운영체제와 응용프로그램 사이에서 소통할수 있게 해주는 언어 혹은 메시지이다.

가장 많이 쓰이는 REST api 는 REST를 기반으로 만들어진 api이다

REST란 Representational State Transfer 의 약자로

자원을 이름으로 구분하여 해당 자원의 상태를 주고받는 모든 것을 의미한다

즉,

> **REST란?**
>
> 1. HTTP URI(Uniform Resource Identifier)를 통해 자원(Resource)을 명시하고,
> 2. HTTP Method(POST, GET, PUT, DELETE, PATCH 등)를 통해
> 3. 해당 자원(URI)에 대한 CRUD Operation을 적용하는 것을 의미합니다.

> **REST의 구성요소**
>
> 1. **자원(Resource) : HTTP URI**
> 2. **자원에 대한 행위(Verb) : HTTP Method**
> 3. **자원에 대한 행위의 내용 (Representations) : HTTP Message Pay Load**

CRUD 동작 과정은 다음 포스팅을 참고하길 바란다

[CRUD Operations - What is CRUD?](https://www.freecodecamp.org/news/crud-operations-explained/)

REST 와 api에 대한 대략적인 설명은 여기까지 하고,

이제 GrapQL의 생성 배경에 대한 얘기를 해보도록 하겠다

### GraphQL 생성 배경

GraphQL은 애초부터 기존 REST api 의 단점을 보완하려고 만들어진 api용 쿼리 언어이다.

다음은 초기 GraphQL의 생성 과정이다

[GraphQL](https://github.com/graphql)

링크를 따라 들어가면 GraphQL에 관한 specification 이 있다

![스크린샷 2023-01-16 오후 5.50.37.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/285cd2d8-6307-4011-8d34-6614e120f8bc/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2023-01-16_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_5.50.37.png)

읽어보면 GraphQL은 facebook 에 의해 만들어졌다고 나와있다.

자세한 설명들은 직접 읽어보길 바란다(초기 개념 잡기에 좋다)

### GraphQL과 REST api 의 차이

자 이제 GraphQL이 보완한 REST api의 단점에 대해 알아보자

> **GraphQL 과 REST api 의 차이**
>
> - REST에서는 Resource에 대한 형태 정의와 데이터 요청 방법이 연결되어 있지만, GraphQL에서는 Resource에 대한 형태 정의와 데이터 요청이 완전히 분리되어 있습니다.
> - REST에서는 Resource의 크기와 형태를 서버에서 결정하지만, GraphQL에서는 Resource에 대한 정보만 정의하고, 필요한 크기와 형태는 client단에서 요청 시 결정합니다.
> - REST에서는 URI가 Resource를 나타내고 Method가 작업의 유형을 나타내지만, GraphQL에서는 GraphQL Schema가 Resource를 나타내고 Query, Mutation 타입이 작업의 유형을 나타냅니다.
> - REST에서는 여러 Resource에 접근하고자 할 때 여러 번의 요청이 필요하지만, GraphQL에서는 한번의 요청에서 여러 Resource에 접근할 수 있습니다.
> - REST에서 각 요청은 해당 엔드포인트에 정의된 핸들링 함수를 호출하여 작업을 처리하지만, GraphQL에서는 요청 받은 각 필드에 대한 resolver를 호출하여 작업을 처리합니다.
