---
title: aws_security_group
post-order: 2
---

## 1. AWS Provider 정의

 [AWS Provider](https://kim-dongoh.github.io/terraform/provider/aws/) 참조



## 2. Resource 정의

> [aws_security_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group)

```bash
vi main.tf
```

```hcl
resource "<Resource Type>" "<Resource Name>" {
  name = "<Security Group Name>"
  tags = {
  	<Key>	=	"<Value>"
  }
  
  ingress {
    from_port = 22
    to_port = 22
    protocol = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
  
  ingress {
    from_port = 80
    to_port = 80
    protocol = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
}
```

* `Resource Type`: `aws_security_group`
  * AWS Provider에 정의된 값
  * `Resource Type` 목록은 [AWS Provider](https://registry.terraform.io/providers/hashicorp/aws/latest/docs) 페이지에서 좌측 사이드 바에 검색하면 `Resources` 하위 항목으로 출력
* `Resource Name`: 해당 Resource의 이름을 정의
* `tags`: `Key = Value` 형식의 AWS 지원 태그 지정 가능
  * ex.) `Name = SSH_Security_group`
* `ingress`: AWS 보안 그룹의 인바운드 규칙, 복수 생성하여 복수개의 Port 지정 가능
  * `from_port`: 인바운드 규칙으로 지정할 시작 Port 지정
  * `to_port`: 인바운드 규칙으로 지정할 마지막 Port 지정
    * ex.) `form_port = 10`, `to_port = 20`으로 지정 시 Port 10 ~ Port 20까지의 Port Open
* `cidr_blocks`: CIDR 리스트 설정
