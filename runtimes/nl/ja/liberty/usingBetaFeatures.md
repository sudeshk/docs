---

copyright:
  years: 2015, 2016

---

{:new_window: target="_blank"}
{:codeblock: .codeblock}

# ベータ・フィーチャーの使用
{: #using_beta_features}

*最終更新日時: 2016 年 6 月 10 日*
{: .last-updated}

Liberty ベータ・フィーチャーによって、将来の Liberty リリースに含まれる可能性のある新しい機能およびプログラミング・モデルに早期にアクセスできます。大部分のベータ・フィーチャーは、Bluemix にデプロイされたアプリケーションでも使用できます。

**重要**: ベータ・フィーチャーは開発およびテスト目的のためにのみ提供され、実動での使用には向いていない場合があります。完全な利用条件については、[ベータのご使用条件](http://public.dhe.ibm.com/ibmdl/export/pub/software/websphere/wasdev/downloads/wlp/beta/lafiles/en.html)を参照してください。

Bluemix で使用可能な Liberty ベータ・フィーチャー
<table>
<tr>
<th align="left">フィーチャー</th>
<th align="left">フィーチャー</th>
<th align="left">フィーチャー</th>
<th align="left">フィーチャー</th>
</tr>

<tr>
<td>bluemixLogCollector-1.1</td>
<td>cloudant-1.0</td>
<td>httpWhiteboard-1.0</td>
<td>logstashCollector-1.1</td>
</tr>

<tr>
<td>osgiBundle-1.0</td>
<td>passwordUtilities-1.0</td>
<td></td>
<td></td>
<td></td>
</tr>

</table>

Bluemix で Liberty ベータ・フィーチャーを使用するには、以下を行う必要があります。

1. 以下の例のように、server.xml ファイルで 1 つ以上のベータ・フィーチャーを使用可能にして、[サーバー・ディレクトリーまたはパッケージ化サーバーをデプロイ](optionsForPushing.html)します。

```
    <server>
        <featureManager>
            <feature>jsp-2.3</feature>
            <feature>passwordUtilities-1.0</feature>
        </featureManager>
    </server>
```
{: #codeblock}

2.  **IBM_LIBERTY_BETA** 環境変数を **true** に設定します。この変数は、アプリケーション用にベータ・フィーチャーをインストールして使用可能にするよう Liberty ビルドパックに指示します。例えば、以下のように指定します。
  * cf コマンド・ライン・ツールを使用する場合
```
       $ cf set-env <yourappname> IBM_LIBERTY_BETA true```
{: #codeblock}

  * manifest.yml ファイルを使用する場合
```
      env:
          IBM_LIBERTY_BETA: "true"```

3. **JBP_CONFIG_LIBERTY** 環境変数を **"version: +"** に設定します。この変数は、ベータ・フィーチャーをサポートする [Liberty ベータ・ランタイム](buildpackDefaults.html#liberty_versions)を使用可能にします。例えば、以下のように指定します。
  * cf コマンド・ライン・ツールを使用する場合
```
       $ cf set-env <yourappname> JBP_CONFIG_LIBERTY "version: +"
```
{: #codeblock}

  * manifest.yml ファイルを使用する場合
```
      env:
          JBP_CONFIG_LIBERTY: "version: +"
```

既存のアプリケーション上のベータ・フィーチャーを使用可能にする場合は、環境変数を設定した後でアプリケーションを再ステージングすることを忘れないでください。

{: #codeblock}

# 関連リンク
{: #rellinks}
## 一般
{: #general}
* [Liberty ランタイム](index.html)
* [Liberty プロファイル概要](http://www-01.ibm.com/support/knowledgecenter/SSAW57_8.5.5/com.ibm.websphere.wlp.nd.doc/ae/cwlp_about.html)
