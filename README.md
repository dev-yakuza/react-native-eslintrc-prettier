# Document

- [Description](#description)
- [설명](#설명)
- [説明](#説明)

## Description

This repository is about how to use ESLint, Prettier, Husky and lint-staged for React Native.

You can see the blog post about this repository.

- [Use ESLint, Prettier like Pro on React Native](https://dev-yakuza.github.io/en/react-native/eslint-prettier-husky-lint-staged/)

### Prepare React Native Project

1. Execute the command below to install libraries for ESLint, Prettier, Husky and lint-staged.

    ```bash
    npm install --save-dev eslint-plugin-react @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint-plugin-react-hooks prettier eslint-plugin-prettier husky lint-staged
    ```

1. Copy and paste `.eslintrc.js` and `.prettierrc.js` contents to your React Native project.
1. Create `.prettierignore` on React Native project root folder and copy-paste `.prettierignore` contents
1. Modify `package.json` like below

    ```json
    {
    ...
    "scripts": {
        ...
        "lint": "eslint --ext .tsx --ext .ts src/",
        "format": "prettier --check ./src",
        ...
    },
    "lint-staged": {
        "src/**/*.{ts,tsx}": [
            "eslint --ext .tsx --ext .ts src/ --fix"
        ],
        "./src/**": [
            "prettier --write ."
        ]
    },
    "husky": {
        "hooks": {
        "pre-commit": "lint-staged"
        }
    },
    ...
    }
    ```

### How to use

> Modify your source code and just `git add` and `git commit`.
> Before `git commit`, Husky and lint-staged execute ESLint and Prettier automatically, and fix or find problems of your source code.

If you want to find the problems of your code with ESLint and Prettier,

Execute the command below to check the source code with `ESLint`.

```bash
npm run lint
```

Execute the command below to check the source code with `Prettier`.

```bash
npm run format
```

## 설명

이 저장소(Repository)는 React Native 프로젝트에서 ESLint, Prettier, Husky 그리고 lint-staged를 어떻게 사용하는지에 대해 설명하고 있습니다.

이 저장소(Repository)에 관한 자세한 내용은 아래에 블로그 포스트를 참고하시기 바랍니다.

- [React Native에서 ESLint, Prettier를 프로처럼 사용하기](https://dev-yakuza.github.io/ko/react-native/eslint-prettier-husky-lint-staged/)

### React Native 프로젝트 준비하기

1. 아래에 명령어를 실행하여 ESLint, Prettier, Husky 그리고 lint-staged에 필요한 라이브러리를 설치합니다..

    ```bash
    npm install --save-dev eslint-plugin-react @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint-plugin-react-hooks prettier eslint-plugin-prettier husky lint-staged
    ```

1. `.eslintrc.js`의 내용과 `.prettierrc.js`의 내용을 자신의 React Native 프로젝트에 복사 붙여넣기를 합니다.
1. React Native 프로젝트의 root 폴더에 `.prettierignore` 파일을 생성하고 `.prettierignore` 내용을 복사 붙여넣기합니다.
1. `package.json`을 아래와 같이 수정합니다.

    ```json
    {
    ...
    "scripts": {
        ...
        "lint": "eslint --ext .tsx --ext .ts src/",
        "format": "prettier --check ./src",
        ...
    },
    "lint-staged": {
        "src/**/*.{ts,tsx}": [
            "eslint --ext .tsx --ext .ts src/ --fix"
        ],
        "./src/**": [
            "prettier --write ."
        ]
    },
    "husky": {
        "hooks": {
        "pre-commit": "lint-staged"
        }
    },
    ...
    }
    ```

### 사용법

> 자신의 소스코드를 수정하고 `git add` 그리고 `git commit`을 합니다.
> `git commit`이 실행되기전에, Husky와 lint-staged가 ESLint 와 Prettier를 자동으로 실행하고, 소스코드의 문제점을 고치고 찾아줍니다.

만약 ESLint와 Prettier를 사용하여 자신의 소스코드의 문제점을 찾고 싶다면,

아래에 명령어를 사용하여 `ESLint`로 자신의 소스코드를 검사합니다.

```bash
npm run lint
```

아래에 명령어를 사용하여 `Prettier`로 자신의 소스코드를 검사합니다.

```bash
npm run format
```

## 説明

このレポジトリ(Repository)はReact NativeのプロジェクトへESLint, Prettier, Husky そして lint-stagedを使う方法について説明しております。

このレポジトリ(Repository)に関して詳しい内容は下記のブログポストを参考してください。

- [React NativeでESLint, Prettierを使う方法](https://dev-yakuza.github.io/react-native/eslint-prettier-husky-lint-staged/)

### React Nativeのプロジェクトの準備

1. 下記のコマンドを実行してESLint, Prettier, Husky そしてlint-stagedへ必要なライブラリをインストールします。
    ```bash
    npm install --save-dev eslint-plugin-react @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint-plugin-react-hooks prettier eslint-plugin-prettier husky lint-staged
    ```

1. `.eslintrc.js`の内容と`.prettierrc.js`の内容を自分のReact Nativeプロジェクトへコピペします。
1. React Nativeのプロジェクトのrootフォルダへ`.prettierignore`ファイルを生成して、`.prettierignore`の内容をコピペします。
1. `package.json`を下記のように修正します。

    ```json
    {
    ...
    "scripts": {
        ...
        "lint": "eslint --ext .tsx --ext .ts src/",
        "format": "prettier --check ./src",
        ...
    },
    "lint-staged": {
        "src/**/*.{ts,tsx}": [
            "eslint --ext .tsx --ext .ts src/ --fix"
        ],
        "./src/**": [
            "prettier --write ."
        ]
    },
    "husky": {
        "hooks": {
        "pre-commit": "lint-staged"
        }
    },
    ...
    }
    ```

### 使い方

> 自分のソースコードを修正して`git add`と`git commit`をします。
> `git commit`が実行される前、Huskyとlint-stagedがESLintとPrettierを自動的に実行して、ソースコードの問題点を直したり、探したりします。

もしESLintとPrettierを使って自分のソースコードの問題点を探したい場合、

下記のコマンドを使って`ESLint`で自分のソースコードを検査します。

```bash
npm run lint
```

下記のコマンドを使って`Prettier`で自分のソースコードを検査します。

```bash
npm run format
```
