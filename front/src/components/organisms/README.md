## src/componets/organisms

特定のページで使用されるコンポーネントがまとめてあります。

## ルール

- 単体で意味を持つコンポーネントになっている
- hooks などの副作用を持つことは可能（必須ではない）
- 単一のプロジェクトに依存するコンポーネントでも良い
- 様々なライブラリに依存しても良い

## テスト観点

### UI テスト (Component)

- 意図した role 属性でクエリできているかを確認  
   expect(getByRole( "role 属性" )).toBeInTheDocument();
- storybook 内で定義した Container で正常な値が渡される前提のテストを行う

その他必要であれば、ラベルや保持している値などに関してのテストも行う

### ロジックテスト(Container)

ロジックを storybook 経由ではなく直接 Container を読み込んでテストを行う

- ロジックに非同期通信が含まれている場合は非同期通信
- 渡された値が Component で必要な形に加工されているか
- hook やライブラリが正しく使用できているか

以上の項目と必要に応じてこのコンポーネントが持つ機能についてテストを行う。