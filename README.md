

### 关于搭建的流程
- 创建仓库，http://yourname.github.io；
- 创建两个分支：master 与 hexo；
- 设置hexo为默认分支（因为我们只需要手动管理这个分支上的Hexo网站文件）；
- 使用git clone git@github.com:yourname/yourname.github.io.git拷贝仓库；
- 在本地http://youname.github.io文件夹下通过Git bash依次执行
    
    ```
     npm install hexo
     hexo init
     npm install
     npm install hexo-deployer-git
     #（此时当前分支应显示为hexo）
    ``` 

- 修改_config.yml中的deploy参数，分支应为master；
- 依次执行

    ```
        git add .
        git commit -m "..."
        git push origin hexo

    ```

- 执行`hexo g -d`生成网站并部署到GitHub上。
- 这样一来，在GitHub上两个分支，一个hexo分支用来存放网站的原始文件，一个master分支用来存放生成的静态网页。

 

### 关于日常的改动流程在本地对博客进行修改
>（添加新博文、修改样式等等）后，通过下面的流程进行管理。

```
    git add .
    git commit -m "..."
    git push origin hexo
```

此时当前分支应为hexo
然后才执行
`hexo g -d`
发布网站到master分支上。虽然两个过程顺序调转一般不会有问题，不过逻辑上这样的顺序是绝对没问题的（例如突然死机要重装了，悲催....的情况，调转顺序就有问题了）。
