## 2.3. アプリケーション・アーキテクチャ

### 2.3.1. 処理方式共通

#### 2.3.1.1. アプリケーションフレームワーク
本システムではアプリケーションフレームワークとして Spring Framework (Spring Boot) を採用する。  
Spring Framework はクラウドネイティブアーキテクチャを実現しており、本システムでも今後クラウドサービスを活用し、  
先進的な技術を活用した開発を推進する想定であるため、Spring Framework を採用した。

Spring Framework (Spring Boot) については、詳細は以下のリファレンスを参照すること。

- https://docs.spring.io/spring-framework/docs/6.1/reference/html/
- https://docs.spring.io/spring-boot/docs/3.2.x/reference/html/

※非公式・有志による日本語訳  
- https://spring.pleiades.io/spring-framework/6.1/  
- https://spring.pleiades.io/spring-boot/docs/3.2.x/reference/html/

また、Spring Framework だけでは対応しきれない機能について Nablrch Application Framework を部分的に利用することで機能不足を補う。  
Nablrch Application Framework について、詳細は以下のリファレンスを参照すること。  

- https://nablarch.github.io/docs/6/doc/

---

#### 2.3.1.2. DBアクセスフレームワーク
本システムでは DB アクセスフレームワークとして MyBatis を採用する。  
MyBatis は広く利用されている SQL マッパーで、Spring Boot と統合可能である。  
また、Spring Batch 向けの部品も提供されており、相性が良い。

MyBatis については、詳細は以下の公式リファレンスを参照すること。  

- https://mybatis.org/mybatis-3/ja/

Spring Framework を利用する際、MyBatis 以外にも DB アクセスフレームワークの選定候補はいくつか存在するが、それらを採用しない理由を以下に示す。

| DBアクセスフレームワーク | 採用しない理由 |
|----------------------|------------------------------------------------------------------|
| JPA                  | 抽象化のマッパーが厚く、学習コストが高く使いこなすには理解が必要となり、大人数での開発には不向き。 |
| JDBC Template        | シンプルで扱いやすいが、低レベルな API のため、生産性は高いとは言えない。 |
| Doma                 | シンプルな SQL マッパーだが、Spring Batch 向けの部品が存在しない。 |

---

### 2.3.2. Web処理方式
本システムの Web 処理方式で利用するアプリケーション・アーキテクチャは Spring Web MVC をベースとする。  

- https://docs.spring.io/spring-framework/reference/web.html  
※非公式・有志による日本語訳  
- https://spring.pleiades.io/spring-framework/6.1/web.html  

---

### 2.3.3. API処理方式
本システムの API 処理方式で利用するアプリケーション・アーキテクチャは Spring Web MVC をベースとする。  
※参考リソースは Web 処理方式と同様。

---

### 2.3.4. バッチ処理方式
本システムのバッチ処理方式で利用するアプリケーション・アーキテクチャは Spring Batch とする。  

Spring Batch については以下のリファレンスを参照すること。

- https://docs.spring.io/spring-batch/reference/5.1/index.html  

※非公式・有志による日本語訳  
- https://spring.pleiades.io/spring-batch/reference/5.1/index.html  
