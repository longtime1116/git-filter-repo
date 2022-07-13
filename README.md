# git-filter-repo-sample


- dev1 ブランチを作って、secret.txtを追加して、mainにmerge
- dev2 ブランチを作って、file.txtを追加して、mainにmerge
- dev3 ブランチを作って、ファイルを新たに追加して、PR作っておく
- 新たにcloneしたうえで、main ブランチにて、

```sh
git filter-repo --replace-text <(echo "old==>new")
git remote add origin git@github.com:longtime1116/git-filter-repo.git
git push origin --force --all
```

- これをすると、secret.txt の文字列が置換されていることがわかる

- 注意点
  - https://github.com/longtime1116/git-filter-repo/pull/1/files
    - PRには残っている。https://docs.github.com/ja/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository#fully-removing-the-data-from-github
  - 以前にcloneした場所ではdev3は元になるmainのcommit idとかが変わってしまっているので、諸々厳しい。再度cloneしてもらうのが望ましい。
