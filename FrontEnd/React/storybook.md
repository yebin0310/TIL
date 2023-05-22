## Stroybook이란?

<hr/>

> Storybook은 컴포넌트 단위의 UI 개발 도구이다.
> React 프로젝트 안에 있는 많은 컴포넌트들을 문서화 할 수 있다

official-gsm 을 하면서 story book 이란걸 처음 도입해보았다
프론트엔드에서의 테스트는 백엔드와 비교했을때 어려운 편이다.
(백엔드는 보통 postman 을 이용하여 테스팅한다)
테스트를 하려면 `mocking` 이라는 과정을 거쳐야 하는데
`mocking`은 보통 테스트 프레임워크나 도구를 사용하여 진행한다.
프론트엔드에서는 Jest, Sinon, Axios Mock Adapter 등이 쓰인다.

하지만 `storybook`을 이용하면 컴포넌트별로 테스트 할 수 있다.
그리고 비슷한 형태로 만들어지는 컴포넌트들을 `storybook` 을 활용하여
더욱 효율적이게 사용 할 수 있다.

아래는 내가 만든 storybook 의 대략적인 구조이다
아래와 같이 만든다면 `isActive`가 `true` 일때와 `false` 일때를
테스팅할 수 있다.

```ts
import Category from ".";
import { Meta, StoryObj } from "@storybook/react";

export default {
  title: "admin/Category",
  component: Category,
  parameters: {},
} as Meta<typeof Category>;

type Story = StoryObj<typeof Category>;

export const Primary: Story = {
  args: {
    isActive: true,
  },
};

export const isActive: Story = {
  args: {
    ...Primary.args,
    isActive: false,
  },
};
```
