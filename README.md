## JRE のスポンサーオファーを無効にするGPO

### コレは何？

JRE(Javaランタイム)のインストーラがアップデートのたびに ASK ツールバーとか召喚するのがウザ過ぎるので無効にするグループポリシー定義ファイルです。  
Active Directory 環境だと一網打尽にできます。

CustomADMX(http://customadmx.sourceforge.net/) の JRE 定義をベースにしています。

### 使い方

- Active Directory のセントラルストアに定義ファイルを置きます。

`\\(DOMAIN_FQDN)\SYSVOL\(DOMAIN_FQDN)\Policies\PolicyDefinitions`

- 日本語環境だと、en-US フォルダの中身を ja-JP フォルダにもコピーします

- 以下のグループポリシーを設定します

`コンピューターの構成/管理用テンプレート/Custom Policies/Oracle Corporation/Java Runtime Environment/Update`  
`Disable Sponsor Offers :有効`

- OUに割り当てて gpupdate /force ！

### ライセンス

ベースにした CustomADMX(http://customadmx.sourceforge.net/) に従い GPLv2(http://www.gnu.org/licenses/gpl-2.0.html) です。

