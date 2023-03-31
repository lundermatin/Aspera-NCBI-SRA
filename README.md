# -Aspera-NCBI-SRA-
使用Aspera从NCBI高速下载SRA数据
要使用Aspera从NCBI高速下载SRA数据，请按照以下步骤操作：

一、下载Aspera客户端，首先，您需要在计算机上安装Aspera客户端。Aspera提供客户端的下载链接，请根据您的操作系统下载并安装适当的版本
1.在linux上使用conda安装Aspera，打开终端并激活您的conda环境。
 然后运行以下命令来安装Aspera：
 
conda install aspera-cli

安装完成后，您可以通过运行以下命令来验证Aspera是否已正确安装：

ascp -h 

如果您看到类似于以下内容的输出，则表示Aspera已成功安装：

Usage: ascp [OPTIONS] SOURCE... DESTINATION ... 

2.查找密钥（后面会用到）

which ascp

二、获取SRA数据的链接，打开NCBI网站

https://sra-explorer.info/#

1.在搜索框中输入你要下载的数据id
![Image text](https://github.com/lundermatin/image/blob/main/image.png)

2.添加下载

3.修改并复制命令

4.使用Aspera下载SRA数据 打开终端或命令提示符窗口，并输入以下命令：

ascp -QT -l 300m -P33001 -i ~/miniconda3/envs/gene/etc/asperaweb_id_dsa.openssh era-fasp@fasp.sra.ebi.ac.uk:vol1/fastq/SRRXXX/SRRXXXXXX/SRRXXXXXX_1.fastq.gz . 

在上面的命令中，请确保将“~/miniconda3/envs/gene/etc/asperaweb_id_dsa.openssh”替换为您计算机上Aspera的密钥路径。
当您输入完命令后，Aspera将开始从NCBI下载SRA数据。

参考自【NCBI】批量(Snakemake)、高速(Aspera)下载SRA数据-哔哩哔哩 https://b23.tv/zv3vSDM
