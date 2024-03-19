Ubuntu GUI登录：
RDP登录，输入Public IP和Username，Port选择3389
 

安装VM驱动：
1、	使用SSH打开，输入Public IP和Username
 
2、	进入后输入密码
3、	进入root
4、	查看终端配置
ubuntu-drivers devices
5、	选择合适的版本进行安装
（这一步可能由于网络波动问题出现404错误，过段时间再重试一下）
sudo apt install nvidia-driver-535
6、测试是否安装成功
nvidia-smi
 

安装CUDA
1、	登陆官网，选择合适的版本（低于本机CUDA Version）
2、	根据配置获取下载指令
 
3、	安装
sudo sh cuda_11.6.2_510.47.03_linux.run
4、	依次操作：选择continue、输入accept、取消勾选Driver
5、	配置环境变量
vim ~/.bashrc
6、	添加以下内容
export PATH=$PATH:/usr/local/cuda/bin  
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda/lib64
7、	验证是否安装成功
source ~/.bashrc
nvcc -V
 

使用Pycharm
cd /opt/pycharm-community-2020.2.3/bin
./pycharm.sh
（使用过程中不要关闭终端）
