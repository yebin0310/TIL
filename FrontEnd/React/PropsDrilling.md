## prop drilling 이란?

<hr/>

> A컴포넌트에서 D컴포넌트로 필요한 정보를 넘겨줄때
> 정보가 필요없는 B,C 컴포넌트도 데이터를 전달받는 현상을 말한다.

전달한 prop이 3~4개면 문제가 되지 않지만,
그 수가 많아지면 해당 코드를 추적(이해)하기가 어려워진다

```jsx
import React from "react";
import "./styles.css";

export default function App() {
  return (
    <div className="App">
      <FirstComponent content="Who needs me?" />
    </div>
  );
}

function FirstComponent({ content }) {
  return (
    <div>
      <h3>I am the first component</h3>;
      <SecondComponent content={content} />|
    </div>
  );
}

function SecondComponent({ content }) {
  return (
    <div>
      <h3>I am the second component</h3>;
      <ThirdComponent content={content} />
    </div>
  );
}

function ThirdComponent({ content }) {
  return (
    <div>
      <h3>I am the third component</h3>;
      <ComponentNeedingProps content={content} />
    </div>
  );
}

function ComponentNeedingProps({ content }) {
  return <h3>{content}</h3>;
}
```

## prop drilling 을 해결하려면?

<hr/>

> prop drilling을 해결하는 방법에는 두가지가있다

1. 상태관리 라이브러리를 이용한다(Redux,jotai,zustand)
2. children을 이용한다

##### 상태관리 라이브러리

- App.tsx

```jsx
import React, { useState } from "react";
import { MainScreen } from "./MainScreen";

export interface IUser {
  id: number;
  name: string;
  photoURL?: string;
}

function App() {
  const [user] =
    useState <
    IUser >
    {
      id: 2,
      name: "박상준",
      photoURL: "dfkslkekls.aws.wela.png",
    };

  return <MainScreen {...user} />;
}
export default App;
```

- MainScreen.tsx

```jsx
import React from "react";
import { IUser } from "./App";
import { Header } from "./Header";

export const MainScreen = (user: IUser): JSX.Element => {
  return (
    <div>
      <Header {...user} />
    </div>
  );
};
```

- Header.tsx

```jsx
import React from "react";
import { IUser } from "./App";

export const Header = (user: IUser) => {
  return (
    <div>
      This is Google Page, {user.id}, {user.photoURL}, {user.name}
    </div>
  );
};
```

<hr/>
##### children 이용

```jsx
import React from "react";
import "./styles.css";

export default function App() {
  const content = "Who needs me?";
  return (
    <div className="App">
      <FirstComponent>
        <SecondComponent>
          <ThirdComponent>
            <ComponentNeedingProps content={content} />
          </ThirdComponent>
        </SecondComponent>
      </FirstComponent>
    </div>
  );
}

function FirstComponent({ children }) {
  return (
    <div>
      <h3>I am the first component</h3>;{children}
    </div>
  );
}

function SecondComponent({ children }) {
  return (
    <div>
      <h3>I am the second component</h3>;{children}
    </div>
  );
}

function ThirdComponent({ children }) {
  return (
    <div>
      <h3>I am the third component</h3>
      {children}
    </div>
  );
}

function ComponentNeedingProps({ content }) {
  return <h3>{content}</h3>;
}
```
