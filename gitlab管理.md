## 管理员

#### 可见性设置
初始进入后, 到 [http://gitlab_serverip:port/admin/application_settings](http://gitlab_serverip:port/admin/application_settings) 里把所有 `visibility` 相关的默认值都设置为 `Internal`(登录后的用户才能看见)

可见性详细说明: [http://gitlab_serverip:port/help/public_access/public_access](http://gitlab_serverip:port/help/public_access/public_access)

#### `Account and Limit Settings` 设置
* `Default projects limit` 每个用户默认可创建的仓库限制, 可以适当调整高一点
* `Maximum attachment size` 附件上传大小限制

#### `Sign-in Restrictions` 设置
* `Sign-up enabled` 是否允许任意人注册帐号(不允许是只能由管理员创建后才能登录)
* `Sign-in enabled` 是否允许登录(不允许时由其它登录方式控制, 例如 LDAP 等, 非常不建议取消)
* `Restricted domains for sign-ups` 限定新用户注册时的邮箱后缀

其它保持默认即可

#### `Users` 管理
管理员手动新建用户时, 记得邮箱需要正确, 能收到邮件, gitlab 会自动发一封邮件到该邮箱来重置密码  
用户自己新注册帐号时, 邮箱也需要是正确的, 以后很多 gitlab 的通知都会通过邮箱发送
* `Access` 设置
    * `Projects limit` 该用户可创建的仓库数量限制
    * `Can create group` 该用户是否可以创建组
    * `Admin` 该用户是否管理员

#### `Group` 管理
Group 是用来对仓库分组的, 用户创建仓库时, 如果不在 group 里创建, 默认的命名空间是当前自己用户, 新创建的工程只有自己能访问, 别的用户需要访问时则需要仓库的拥有者对需要访问的人(project members)一个一个加权限. 如果仓库多了之后会很麻烦

把仓库都归到一个 group 后, 该 group 里的人员(group members)都自动获得对这些仓库的访问权限

详细的权限说明在这里: [http://gitlab_serverip:port/help/permissions/permissions](http://gitlab_serverip:port/help/permissions/permissions)
