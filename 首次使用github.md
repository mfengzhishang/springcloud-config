进入git bash界面然后：
**第一步验证邮箱与GitHub注册时输入的是否一致**


git config --global --list 
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190521165825941.png)
**第二步，设置全局用户名和邮箱**


通过git config --global [user.name](http://user.name/)  “mfengzhishang”，git config --global user.email "649443778@qq.com"（这里得名字和邮箱都是注册github时用的）。

**第三步生成密钥**


ssh-keygen -t rsa -C "649443778@qq.com"，一路回车，在出现选择时输入Y，再一路回车直到生成密钥。会在C:/Users/Administrator/\.ssh/路径下生成一个.ssh文件夹，密钥就存储在其中。
![img](https://img-blog.csdnimg.cn/20190521170341260.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNzY4OTQ2,size_16,color_FFFFFF,t_70)
**第四步，到git仓库，添加秘钥**

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190521165333581.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190521165414619.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190521165436687.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/2019052116562173.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNzY4OTQ2,size_16,color_FFFFFF,t_70)
点击Add SSH key

**第五部测试一下通不通**


ssh -T git@github.com 测试一下通不通，通了显示如下
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190521165223872.png)
即可正常使用。
不通就是
ssh-agent -s
ssh-add ~/.ssh/id_rsa 操作这两步。

