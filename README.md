# ServerStudy5Cloud
GDSC 5기 Server 파트 스터디 5주차를 위한 실습용 리포지토리입니다.
Spring Boot에서 AWS S3의 객체를 조회하고, 이미지를 업로드하는 기능을 구현합니다.

## To-Do List
1. application.yml 파일을 수정해주세요.
```yaml
cloud:
  aws:
    s3:
      bucket: # [Bucket-Name]
    stack.auto: false
    region.static: ap-northeast-2
    credentials:
      access-key: # [Access-Key]
      secret-key: # [Secret-key]
```

2. S3Controller.java 파일을 수정해주세요.
```java
@GetMapping("/")
public String listFiles(Model model) {
    //getUrl로 객체 URL 가져온 후, List<String>에 넣어 index.html에 반환하기
    return "index";
}

@PostMapping("/upload")
public String uploadFile(@RequestParam("file") MultipartFile file) {

    //putObject와 setObjectAcl로 이미지 업로드하고 ACL 퍼블릭으로 만들기
    return "redirect:/";

}
```

3. 심화과제: application.yml이 아니라 .env에 Access Key 관련 정보를 넣어, 실수로 깃허브에 Public으로 업로드되는 일이 없도록 구성해보세요.
