# iOSRealRun-cli-17-plus

## 如何使用

### 前置条件

1. 系统是 `Windows` 或 `MacOS`．

2. iPhone 或 iPad 系统版本大于等于 17．

3. ~~Windows 需要安装 iTunes~~ 实测 iOS 17.6 以上 Windows PC 端的 Apple 驱动有 bug, 连接 iTunes 时会无规律断连，但不影响本软件．

4. 安装 `python` 和 `pip`，建议使用 `python 3.9`：[下载 Python 3.9.13](https://www.python.org/downloads/release/python-3913/)．

    安装时建议勾选安装 py 启动器（若已安装过则不用）．

5. **重要**: 只能有一台 iPhone 或 iPad 连接到电脑，否则会出问题．


### 步骤

1. 克隆本项目到本地并进入项目目录；

2. 安装依赖：

    > 为避免依赖和 python 版本冲突，最好使用虚拟环境．

    - 如果使用虚拟环境

        在命令行下运行

        ```shell
        py -3.9 -m venv .venv
        ```

        在 Windows 下，运行

        ```powershell
        .\.venv\Scripts\activate
        ```

        **注意**：Windows 下运行上面的命令可能会因为 `PowerShell` 的执行政策而报错，在管理员模式下的 `PowerShell` 运行以下命令后再运行上面命令即可．

        ```powershell
        Set-ExecutionPolicy -ExecutionPolicy Bypass
        ```

        在 MacOS 下，运行

        ```shell
        source .venv/bin/activate
        ```

        这样进入了 `python 3.9` 的虚拟环境．

    安装依赖文件，运行

    ```shell
    pip install -r requirements.txt
    ```

3. 修改配置和路线文件．（见 [这里](https://github.com/iOSRealRun/iOSRealRun-cli/blob/main/README.md#%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95) 的 4、5、7 步）

4. 将设备连接到电脑，解锁，如果请求信任的提示框，请点击信任．

5. Windows **以管理员身份** 打开终端（或 PowerShell），先进入项目目录，然后执行以下命令

    > 如果之前在虚拟环境下安装依赖，请确保你在虚拟环境下执行以下命令．若命令行最左端有 `(.venv)` 字段则说明已进入虚拟环境，否则参照第 2 步进入虚拟环境．

    ```powershell
    python main.py
    ```
    MacOS 打开终端，先进入项目目录，然后执行以下命令  

    ```shell
    sudo python3 main.py
    ```

    > 需要管理员或 root 权限是因为需要创建 tun 设备  

6. 按照提示操作，在第 3 步时请确保设备已连接，解锁并信任．若仍无法成功可能是设备问题或者是 Apple 在 Windows 上的驱动问题．本方法实测在 `iOS 18.1.1` 下有效，即使 iPhone 甚至无法连接上 Windows 上的 iTunes．

7. 结束请务必使用 `Ctrl + C` 终止程序，否则无法恢复定位．或者直接重启手机．

8. 如果定位未恢复，可以重启手机解决
