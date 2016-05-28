.. image:: https://img.shields.io/badge/docs-latest-brightgreen.svg


Welcome to learn_readthedocs Documentation
==========================================
`ReadTheDocs <https://readthedocs.org/>`_ 是一个能在你每次Commit到GitHub后, 自动Build并部署你的文档网站的服务。免除了繁琐的自行Build文档, 然后部署网站的过程。

ReadTheDocs使用Python社区的 `Sphinx <http://www.sphinx-doc.org/en/stable/>`_ 文档创建引擎。


使用ReadTheDocs服务
-------------------
请按照下面的流程, 学习如何使用ReadTheDocs。你可以Folk `此项目 <https://github.com/MacHu-GWU/learn_readthedocs-project>`_ 用于练习。然后可以在 `这里看到本项目的例子的成品网站 <http://learn-readthedocs.readthedocs.io/zh/latest/>`_。


第一步, 创建你的文档网站, 并将代码放在GitHub上
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
首先, 你需要在 `GitHub <https://github.com/>`_ 上 `创建 <https://github.com/new>`_ 一个代码库。然后使用Sphinx `创建 <http://www.sphinx-doc.org/en/stable/tutorial.html>`_ 你的文档网站, 确保能在本地成功的Build。


第二步, 设置ReadTheDocs
~~~~~~~~~~~~~~~~~~~~~~~
首先你要将项目关联到ReadTheDocs。你需要在 `控制面板 <https://readthedocs.org/dashboard/>`_ `导入 <https://readthedocs.org/dashboard/import/?>`_ 你的项目。

然后, 你需要进入Admin菜单进行一些设置。下面列出了一些比较容易出问题的设置的解说:

- Language: 如果你的文档中是纯英文, 就选择默认的English; 如果是中文文档, 就选择Chinese。
- Programming Language: 如果你是纯文档, 就选择Only Words; 如果需要从Python代码中自动生成文档, 则选择Python2。

高级设置:

- Install Project: 如果你需要从代码中自动生成文档, 则你需要确保你的项目是可import的。所以当然首先需要安装你的项目。勾选此项使得在Build文档前先安装你的包。
- Requirements File: 如果你需要从代码中自动生成文档, 则你需要确保你的项目是可import的。但你的项目可能依赖一些其他的包才能够运行。这些依赖就在 `requirments.txt <https://pip.pypa.io/en/stable/user_guide/#requirements-files>`_ 文件中定义的。
- Single version: 请勾选此选项, 保持网站默认使用最新的文档。
- Python interpreter: Build文档的Python虚拟环境, 请确保和你的项目开发环境一致。

**至此, 每当你有新的更新时, ReadTheDocs就会自动Build你的网站了, 如果成功了, 则会自动部署。如果失败了, 你可以查看Build日志了解发生了什么事。**


其他替代方案
------------
任何支持静态网站部署的服务都可以用于部署你的文档网站。例如AWS的 `S3 <https://aws.amazon.com/s3/>`_ 服务提供了自动部署静态网站的服务。具体做法请参考 `官方文档 <http://docs.aws.amazon.com/AmazonS3/latest/dev/WebsiteHosting.html>`_。你所要做的只是将文档网站文件的压缩包上传到S3即可。

你可以自行尝试其他的服务提供商。


ReadTheDocs的限制
-----------------
在后台设置界面, 有一个选项叫Language, 默认设置是en(英文)。此时 **不允许文档中出现任何非英文字符**, 若出现了, 则会导致Build失败。所以在我们如果要Build一个中文网站, 则需要将Language设置为Chinese。

2016年6月, 发现ReadTheDocs的域名不太稳定。个人比较偏好使用AWS S3或PyPI的PythonHost部署文档。


附录
----
- `Python开源项目开发指南 <https://github.com/MacHu-GWU/Python-OpenSource-Project-Developer-Guide>`_