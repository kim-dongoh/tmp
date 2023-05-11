---
title: aws_instance
post-order: 1
---

## 1. AWS Provider 정의

 [AWS Provider](https://kim-dongoh.github.io/terraform/provider/aws/) 참조



## 2. Resource 정의

> [aws_instance](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/instance)

```bash
vi main.tf
```

```hcl
resource "<Resource Type>" "<Resource Name>" {
  ami = "<AMI ID>"
  instance_type = "<Instance Type>"
  tags = {
  	<Key> = <Value>
  }
  key_name = "<Public Key Name>"
  vpc_security_group_ids = [
    data.aws_security_group.default.id
  ]
}
```

* `Resource Type`: `aws_instance`
  * AWS Provider에 정의된 값
  * `Resource Type` 목록은 [AWS Provider](https://registry.terraform.io/providers/hashicorp/aws/latest/docs) 페이지에서 좌측 사이드 바에 검색하면 `Resources` 하위 항목으로 출력
* `Resource Name`: 해당 Resource의 이름을 정의
* `ami`: AWS의 AMI ID를 입력
  * ex) `ami-0c6e5afdd23291f73`

* `instance_type`: Instance의 Type을 지정
  * ex) `t2.micro`
* `tags`: `Key = Value` 형식의 AWS 지원 태그 지정 가능
  * ex.) `Name = Test_Instance`
* `key_name`: SSH 접속 시 사용할 개인키와 대칭되는 AWS에 저장된 공개키 명
  * EC2 -> 사이드바 키 페어 -> 이름
* `vpc_security_group_ids`: Instance에 적용할 보안 그룹의 ID 리스트
  * 해당 코드는 default란 Data Source 명을 가진 [aws_security_group Data Source](https://kim-dongoh.github.io/terraform/data_source/aws_security_group)를 참조하여 보안 그룹 ID를 지정