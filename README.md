# RandomWebsiteStar
Star me if you want to star https://github.com/swrdfgd/RandomWebsite since I keep delete this repo and create it again
ข้ามไปยังเนื้อหาหลัก
เอกสาร GitHub
แพ็คเกจ GitHub/การทํางานกับรีจิสทรี GitHub Packages/รีจิสทรีคอนเทนเนอร์
การทํางานกับรีจิสทรีคอนเทนเนอร์
คุณสามารถจัดเก็บและจัดการอิมเมจ Docker และ OCI ในรีจิสทรีคอนเทนเนอร์

ในบทความนี้
เกี่ยวกับรีจิสทรีคอนเทนเนอร์
เกี่ยวกับการสนับสนุนรีจิสทรีคอนเทนเนอร์
การรับรองความถูกต้องกับรีจิสทรีคอนเทนเนอร์
การพุชอิมเมจคอนเทนเนอร์
การดึงอิมเมจคอนเทนเนอร์
การสร้างอิมเมจคอนเทนเนอร์
การติดแท็กรูปภาพคอนเทนเนอร์
การติดฉลากรูปภาพคอนเทนเนอร์
แก้ไข ปัญหา
เกี่ยวกับรีจิสทรีคอนเทนเนอร์
รีจิสทรีคอนเทนเนอร์จะจัดเก็บอิมเมจคอนเทนเนอร์ภายในองค์กรหรือบัญชีส่วนตัวของคุณ และช่วยให้คุณสามารถเชื่อมโยงอิมเมจกับที่เก็บได้ คุณสามารถเลือกได้ว่าจะสืบทอดสิทธิ์จากที่เก็บ หรือตั้งค่าสิทธิ์แบบละเอียดโดยอิสระจากที่เก็บ คุณยังสามารถเข้าถึงอิมเมจคอนเทนเนอร์สาธารณะโดยไม่ระบุตัวตน

เกี่ยวกับการสนับสนุนรีจิสทรีคอนเทนเนอร์
ปัจจุบันรีจิสทรีคอนเทนเนอร์รองรับรูปแบบอิมเมจคอนเทนเนอร์ต่อไปนี้:

Docker Image Manifest v2, Schema 2
ข้อมูลจําเพาะของ Open Container Initiative (OCI)
เมื่อติดตั้งหรือเผยแพร่อิมเมจ Docker รีจิสทรีคอนเทนเนอร์จะรองรับเลเยอร์ต่างประเทศ เช่น อิมเมจ Windows

การรับรองความถูกต้องกับรีจิสทรีคอนเทนเนอร์
โน้ต

GitHub Packages รองรับการรับรองความถูกต้องโดยใช้โทเค็นการเข้าถึงส่วนบุคคล (คลาสสิก) เท่านั้น สําหรับข้อมูลเพิ่มเติม โปรดดู การจัดการโทเค็นการเข้าถึงส่วนบุคคลของคุณ

คุณต้องมีโทเค็นการเข้าถึงเพื่อเผยแพร่ ติดตั้ง และลบแพ็คเกจส่วนตัว ภายใน และสาธารณะ

คุณสามารถใช้โทเค็นการเข้าถึงส่วนบุคคล (คลาสสิก) เพื่อรับรองความถูกต้องกับ GitHub Packages หรือ GitHub API เมื่อคุณสร้างโทเค็นการเข้าถึงส่วนบุคคล (แบบคลาสสิก) คุณสามารถกําหนดขอบเขตที่แตกต่างกันให้กับโทเค็นได้ตามความต้องการของคุณ สําหรับข้อมูลเพิ่มเติมเกี่ยวกับขอบเขตที่เกี่ยวข้องกับแพ็คเกจสําหรับโทเค็นการเข้าถึงส่วนบุคคล (คลาสสิก) โปรดดู เกี่ยวกับสิทธิ์สําหรับแพ็คเกจ GitHub

หากต้องการตรวจสอบสิทธิ์กับรีจิสทรี GitHub Packages ภายในเวิร์กโฟลว์ GitHub Actions คุณสามารถใช้:

GITHUB_TOKEN เพื่อเผยแพร่แพคเกจที่เชื่อมโยงกับที่เก็บเวิร์กโฟลว์
โทเค็นการเข้าถึงส่วนบุคคล (คลาสสิก) ที่มีขอบเขตอย่างน้อยในการติดตั้งแพคเกจที่เชื่อมโยงกับที่เก็บส่วนตัวอื่นๆ (สามารถใช้ได้หากที่เก็บได้รับสิทธิ์การเข้าถึงการอ่านไปยังแพ็กเกจ ดู การกําหนดค่าการควบคุมการเข้าถึงและการมองเห็นของแพ็คเกจ)read:packagesGITHUB_TOKEN
การรับรองความถูกต้องในเวิร์กโฟลว์ GitHub Actions
รีจิสทรีนี้รองรับสิทธิ์แบบละเอียด สําหรับรีจิสทรีที่รองรับสิทธิ์แบบละเอียด หากเวิร์กโฟลว์ GitHub Actions ของคุณใช้โทเค็นการเข้าถึงส่วนบุคคลเพื่อรับรองความถูกต้องกับรีจิสทรี เราขอแนะนําให้คุณอัปเดตเวิร์กโฟลว์ของคุณเพื่อใช้ไฟล์ . สําหรับคําแนะนําเกี่ยวกับการอัปเดตเวิร์กโฟลว์ของคุณที่รับรองความถูกต้องกับรีจิสทรีด้วยโทเค็นการเข้าถึงส่วนบุคคล โปรดดู การเผยแพร่และติดตั้งแพ็คเกจด้วย GitHub ActionsGITHUB_TOKEN

โน้ต

ความสามารถสําหรับเวิร์กโฟลว์ GitHub Actions ในการลบและกู้คืนแพ็คเกจโดยใช้ REST API อยู่ในการแสดงตัวอย่างสาธารณะและอาจมีการเปลี่ยนแปลง

คุณสามารถใช้ในเวิร์กโฟลว์ GitHub Actions เพื่อลบหรือกู้คืนแพ็คเกจโดยใช้ REST API หากโทเค็นมีสิทธิ์ในแพ็คเกจ ที่เก็บที่เผยแพร่แพ็กเกจโดยใช้เวิร์กโฟลว์ และที่เก็บที่คุณเชื่อมต่อกับแพ็กเกจอย่างชัดเจน จะได้รับสิทธิ์ในแพ็กเกจในที่เก็บโดยอัตโนมัติGITHUB_TOKENadminadmin

สําหรับข้อมูลเพิ่มเติมเกี่ยวกับ โปรดดู การตรวจสอบโทเค็นอัตโนมัติ สําหรับข้อมูลเพิ่มเติมเกี่ยวกับแนวทางปฏิบัติที่ดีที่สุดเมื่อใช้รีจิสทรีในการดําเนินการ โปรดดู การเสริมความแข็งแกร่งด้านความปลอดภัยสําหรับ GitHub ActionsGITHUB_TOKEN

คุณยังสามารถเลือกที่จะให้สิทธิ์การเข้าถึงแพ็คเกจอย่างอิสระสําหรับ GitHub Codespaces และ GitHub Actions สําหรับข้อมูลเพิ่มเติม โปรดดู การกําหนดค่าการควบคุมการเข้าถึงและการมองเห็นของแพ็คเกจ และ การกําหนดค่าการควบคุมการเข้าถึงและการมองเห็นของแพ็คเกจ

การรับรองความถูกต้องด้วยโทเค็นการเข้าถึงส่วนบุคคล (คลาสสิก)
โน้ต

GitHub Packages รองรับการรับรองความถูกต้องโดยใช้โทเค็นการเข้าถึงส่วนบุคคล (คลาสสิก) เท่านั้น สําหรับข้อมูลเพิ่มเติม โปรดดู การจัดการโทเค็นการเข้าถึงส่วนบุคคลของคุณ

สร้างโทเค็นการเข้าถึงส่วนบุคคลใหม่ (แบบคลาสสิก) ด้วยขอบเขตที่เหมาะสมสําหรับงานที่คุณต้องการทําให้สําเร็จ หากองค์กรต้องการ SSO คุณต้องเปิดใช้งาน SSO สําหรับโทเค็นใหม่

โน้ต

ตามค่าเริ่มต้น เมื่อคุณเลือกขอบเขตสําหรับโทเค็นการเข้าถึงส่วนบุคคล (คลาสสิก) ในส่วนติดต่อผู้ใช้ ขอบเขตจะถูกเลือกด้วย ขอบเขตนี้ให้การเข้าถึงที่ไม่จําเป็นและกว้างขวาง ซึ่งเราขอแนะนําให้คุณหลีกเลี่ยงการใช้สําหรับเวิร์กโฟลว์ GitHub Actions โดยเฉพาะ สําหรับข้อมูลเพิ่มเติม โปรดดู การเสริมความแข็งแกร่งด้านความปลอดภัยสําหรับ GitHub Actions วิธีแก้ปัญหา คุณสามารถเลือกเฉพาะขอบเขตสําหรับโทเค็นการเข้าถึงส่วนบุคคล (คลาสสิก) ในอินเทอร์เฟซผู้ใช้ด้วย URL นี้:write:packagesreporepowrite:packageshttps://github.com/settings/tokens/new?scopes=write:packages

เลือกขอบเขตเพื่อดาวน์โหลดอิมเมจคอนเทนเนอร์และอ่านข้อมูลเมตาread:packages
เลือกขอบเขตเพื่อดาวน์โหลดและอัปโหลดอิมเมจคอนเทนเนอร์ และอ่านและเขียนข้อมูลเมตาwrite:packages
เลือกขอบเขตเพื่อลบอิมเมจคอนเทนเนอร์delete:packages
สําหรับข้อมูลเพิ่มเติม โปรดดู การจัดการโทเค็นการเข้าถึงส่วนบุคคลของคุณ

บันทึกโทเค็นการเข้าถึงส่วนบุคคลของคุณ (แบบคลาสสิก) เราขอแนะนําให้บันทึกโทเค็นของคุณเป็นตัวแปรสภาพแวดล้อม

export CR_PAT=YOUR_TOKEN
ใช้ CLI สําหรับประเภทคอนเทนเนอร์ของคุณ ให้ลงชื่อเข้าใช้บริการรีจิสทรีคอนเทนเนอร์ที่ .ghcr.io

$ echo $CR_PAT | docker login ghcr.io -u USERNAME --password-stdin
> Login Succeeded
การพุชอิมเมจคอนเทนเนอร์
ตัวอย่างนี้ผลักดันเวอร์ชันล่าสุดของ .IMAGE_NAME

docker push ghcr.io/NAMESPACE/IMAGE_NAME:latest
แทนที่ด้วยชื่อของบัญชีส่วนตัวหรือองค์กรที่คุณต้องการให้มีขอบเขตรูปภาพNAMESPACE

ตัวอย่างนี้ผลักดันเวอร์ชันของรูปภาพ2.5

docker push ghcr.io/NAMESPACE/IMAGE_NAME:2.5
เมื่อคุณเผยแพร่แพ็กเกจเป็นครั้งแรก การมองเห็นเริ่มต้นจะเป็นแบบส่วนตัว หากต้องการเปลี่ยนการมองเห็นหรือตั้งค่าสิทธิ์การเข้าถึง โปรดดู การกําหนดค่าการควบคุมการเข้าถึงและการมองเห็นของแพ็คเกจ คุณสามารถเชื่อมโยงแพคเกจที่เผยแพร่ไปยังที่เก็บโดยใช้อินเทอร์เฟซผู้ใช้หรือบรรทัดคําสั่ง สําหรับข้อมูลเพิ่มเติม โปรดดู การเชื่อมต่อที่เก็บกับแพคเกจ

เมื่อคุณพุชอิมเมจคอนเทนเนอร์จากบรรทัดคําสั่ง อิมเมจจะไม่เชื่อมโยงกับที่เก็บตามค่าเริ่มต้น กรณีนี้แม้ว่าคุณจะแท็กรูปภาพด้วยเนมสเปซที่ตรงกับชื่อของที่เก็บ เช่น .ghcr.io/octocat/my-repo:latest

วิธีที่ง่ายที่สุดในการเชื่อมต่อที่เก็บกับแพคเกจคอนเทนเนอร์คือการเผยแพร่แพคเกจจากเวิร์กโฟลว์โดยใช้ เนื่องจากที่เก็บที่มีเวิร์กโฟลว์จะเชื่อมโยงโดยอัตโนมัติ โปรดทราบว่าจะไม่มีสิทธิ์ในการพุชแพคเกจหากคุณเคยพุชแพคเกจไปยังเนมสเปซเดียวกันก่อนหน้านี้ แต่ยังไม่ได้เชื่อมต่อแพคเกจกับที่เก็บ${{secrets.GITHUB_TOKEN}}GITHUB_TOKEN

ในการเชื่อมต่อที่เก็บเมื่อเผยแพร่อิมเมจจากบรรทัดคําสั่ง และเพื่อให้แน่ใจว่าคุณมีสิทธิ์ที่เหมาะสมเมื่อใช้เวิร์กโฟลว์ GitHub Actions เราขอแนะนําให้เพิ่มป้ายกํากับลงใน . สําหรับข้อมูลเพิ่มเติม โปรดดู "การติดป้ายกํากับอิมเมจคอนเทนเนอร์" ในบทความนี้ และ "การเผยแพร่และติดตั้งแพ็คเกจด้วย GitHub Actions"GITHUB_TOKENorg.opencontainers.image.sourceDockerfile

การดึงอิมเมจคอนเทนเนอร์
ดึงโดยย่อย
เพื่อให้แน่ใจว่าคุณใช้อิมเมจเดียวกันอยู่เสมอ คุณสามารถระบุเวอร์ชันอิมเมจคอนเทนเนอร์ที่คุณต้องการดึงตามค่า SHA ได้digest

เมื่อต้องการค้นหาค่า SHA แบบสรุป ให้ใช้ หรือ และคัดลอกค่า SHA หลังจาก docker inspectdocker pullDigest:

docker inspect ghcr.io/NAMESPACE/IMAGE_NAME
แทนที่ด้วยชื่อของบัญชีส่วนบุคคลหรือองค์กรที่มีขอบเขตรูปภาพNAMESPACE

ลบรูปภาพในเครื่องตามต้องการ

docker rmi ghcr.io/NAMESPACE/IMAGE_NAME:latest
ดึงอิมเมจคอนเทนเนอร์ด้วยชื่ออิมเมจ@YOUR_SHA_VALUE

docker pull ghcr.io/NAMESPACE/IMAGE_NAME@sha256:82jf9a84u29hiasldj289498uhois8498hjs29hkuhs
ดึงตามชื่อ
docker pull ghcr.io/NAMESPACE/IMAGE_NAME
แทนที่ด้วยชื่อของบัญชีส่วนบุคคลหรือองค์กรที่มีขอบเขตรูปภาพNAMESPACE

ดึงตามชื่อและเวอร์ชัน
ตัวอย่าง Docker CLI ที่แสดงอิมเมจที่ดึงโดยชื่อและแท็กเวอร์ชัน:1.14.1

$ docker pull ghcr.io/NAMESPACE/IMAGE_NAME:1.14.1
> 5e35bd43cf78: Pull complete
> 0c48c2209aab: Pull complete
> fd45dd1aad5a: Pull complete
> db6eb50c2d36: Pull complete
> Digest: sha256:ae3b135f133155b3824d8b1f62959ff8a72e9cf9e884d88db7895d8544010d8e
> Status: Downloaded newer image for ghcr.io/NAMESPACE/IMAGE_NAME/release:1.14.1
> ghcr.io/NAMESPACE/IMAGE_NAME/release:1.14.1
แทนที่ด้วยชื่อของบัญชีส่วนบุคคลหรือองค์กรที่มีขอบเขตรูปภาพNAMESPACE

ดึงตามชื่อและเวอร์ชันล่าสุด
$ docker pull ghcr.io/NAMESPACE/IMAGE_NAME:latest
> latest: Pulling from NAMESPACE/IMAGE_NAME
> Digest: sha256:b3d3e366b55f9a54599220198b3db5da8f53592acbbb7dc7e4e9878762fc5344
> Status: Downloaded newer image for ghcr.io/NAMESPACE/IMAGE_NAME:latest
> ghcr.io/NAMESPACE/IMAGE_NAME:latest
แทนที่ด้วยชื่อของบัญชีส่วนบุคคลหรือองค์กรที่มีขอบเขตรูปภาพNAMESPACE

การสร้างอิมเมจคอนเทนเนอร์
This example builds the image:hello_docker

docker build -t hello_docker .
Tagging container images
Find the ID for the Docker image you want to tag.

$ docker images
> REPOSITORY                                            TAG                 IMAGE ID            CREATED             SIZE
> ghcr.io/my-org/hello_docker         latest            38f737a91f39        47 hours ago        91.7MB
> hello-world                                           latest              fce289e99eb9        16 months ago       1.84kB
Tag your Docker image using the image ID and your desired image name and hosting destination.

docker tag 38f737a91f39 ghcr.io/NAMESPACE/NEW_IMAGE_NAME:latest
Replace with the name of the personal account or organization to which you want the image to be scoped.NAMESPACE

Labelling container images
You can use pre-defined annotation keys to add metadata including a description, a license, and a source repository to your container image. Values for supported keys will appear on the package page for the image.

For most images, you can use Docker labels to add the annotation keys to an image. For more information, see LABEL in the official Docker documentation and Pre-Defined Annotation Keys in the repository.opencontainers/image-spec

For multi-arch images, you can add a description to the image by adding the appropriate annotation key to the field in the image's manifest. For more information, see Adding a description to multi-arch images.annotations

The following annotation keys are supported in the Container registry.

กุญแจ	คำอธิบาย
org.opencontainers.image.source	URL ของที่เก็บที่เชื่อมโยงกับแพ็คเกจ สําหรับข้อมูลเพิ่มเติม โปรดดู การเชื่อมต่อที่เก็บกับแพคเกจ
org.opencontainers.image.description	คําอธิบายแบบข้อความอย่างเดียวที่จํากัดไว้ที่ 512 อักขระ คําอธิบายนี้จะปรากฏในหน้าแพ็คเกจ ด้านล่างชื่อของแพ็คเกจ
org.opencontainers.image.licenses	ตัวระบุใบอนุญาต SPDX เช่น "MIT" จํากัดอักขระ 256 ตัว ใบอนุญาตจะปรากฏในหน้าแพ็คเกจในแถบด้านข้าง "รายละเอียด" สําหรับข้อมูลเพิ่มเติม โปรดดู รายการใบอนุญาต SPDX
หากต้องการเพิ่มคีย์เป็นป้ายกํากับ Docker เราขอแนะนําให้ใช้คําสั่งใน . ตัวอย่างเช่น หากคุณเป็นผู้ใช้และเป็นเจ้าของ และรูปภาพของคุณถูกแจกจ่ายภายใต้เงื่อนไขของใบอนุญาต MIT คุณจะต้องเพิ่มบรรทัดต่อไปนี้ลงใน :LABELDockerfileoctocatmy-repoDockerfile

LABEL org.opencontainers.image.source=https://github.com/octocat/my-repo
LABEL org.opencontainers.image.description="My container image"
LABEL org.opencontainers.image.licenses=MIT
โน้ต

หากคุณเผยแพร่แพคเกจที่เชื่อมโยงกับที่เก็บ แพคเกจจะสืบทอดสิทธิ์การเข้าถึงของที่เก็บที่เชื่อมโยงโดยอัตโนมัติ และเวิร์กโฟลว์ GitHub Actions ในที่เก็บที่เชื่อมโยงจะสามารถเข้าถึงแพ็กเกจโดยอัตโนมัติ เว้นแต่องค์กรของคุณจะปิดใช้งานการสืบทอดสิทธิ์การเข้าถึงโดยอัตโนมัติ สําหรับข้อมูลเพิ่มเติม โปรดดู การกําหนดค่าการควบคุมการเข้าถึงและการมองเห็นของแพ็คเกจ

หรือคุณสามารถเพิ่มป้ายกํากับให้กับอิมเมจในเวลาสร้างด้วยคําสั่งdocker build

$ docker build \
 --label "org.opencontainers.image.source=https://github.com/octocat/my-repo" \
 --label "org.opencontainers.image.description=My container image" \
 --label "org.opencontainers.image.licenses=MIT"
การเพิ่มคําอธิบายให้กับรูปภาพแบบหลายส่วนโค้ง
อิมเมจแบบหลายอาร์คคืออิมเมจที่รองรับหลายสถาปัตยกรรม ทํางานโดยอ้างอิงรายการรูปภาพ ซึ่งแต่ละภาพรองรับสถาปัตยกรรมที่แตกต่างกันภายในรายการเดียว

คําอธิบายที่ปรากฏบนหน้าแพคเกจสําหรับรูปภาพแบบหลายส่วนโค้งจะได้มาจากฟิลด์ในรายการของรูปภาพ เช่นเดียวกับป้ายกํากับ Docker คําอธิบายประกอบเป็นวิธีเชื่อมโยงข้อมูลเมตากับรูปภาพ และรองรับคีย์คําอธิบายประกอบที่กําหนดไว้ล่วงหน้า สําหรับข้อมูลเพิ่มเติม โปรดดู คําอธิบายประกอบในที่เก็บannotationsopencontainers/image-spec

เมื่อต้องการให้คําอธิบายสําหรับรูปภาพแบบหลายส่วนโค้ง ให้ตั้งค่าสําหรับคีย์ในฟิลด์ของรายการดังนี้org.opencontainers.image.descriptionannotations

"annotations": {
  "org.opencontainers.image.description": "My multi-arch image"
}
ตัวอย่างเช่น ขั้นตอนเวิร์กโฟลว์ GitHub Actions ต่อไปนี้จะสร้างและผลักดันอิมเมจแบบหลายส่วนโค้ง พารามิเตอร์จะตั้งค่าคําอธิบายสําหรับรูปภาพoutputs

# This workflow uses actions that are not certified by GitHub.
# They are provided by a third-party and are governed by
# separate terms of service, privacy policy, and support
# documentation.

- name: Build and push Docker image
  uses: docker/build-push-action@f2a1d5e99d037542a71f64918e516c093c6f3fc4
  with:
    context: .
    file: ./Dockerfile
    platforms: ${{ matrix.platforms }}
    push: true
    outputs: type=image,name=target,annotation-index.org.opencontainers.image.description=My multi-arch image
แก้ไข ปัญหา
รีจิสทรีคอนเทนเนอร์มีขีดจํากัดขนาด 10 GB สําหรับแต่ละเลเยอร์
รีจิสทรีคอนเทนเนอร์มีขีดจํากัดการหมดเวลา 10 นาทีสําหรับการอัปโหลด
ความช่วยเหลือและการสนับสนุน
ไอคอน Copilot ต่อหน้าการระเบิดของสีสัน
รับคําตอบอย่างรวดเร็ว!
ถามคําถามของคุณกับ Copilot
คุณพบสิ่งที่คุณต้องการหรือไม่?

นโยบายความเป็นส่วนตัว
ช่วยเราทําให้เอกสารเหล่านี้ยอดเยี่ยม!
เอกสาร GitHub ทั้งหมดเป็นโอเพ่นซอร์ส เห็นสิ่งที่ผิดหรือไม่ชัดเจน? ส่งคําขอดึงข้อมูล

เรียนรู้วิธีการมีส่วนร่วม

ยังต้องการความช่วยเหลืออยู่ใช่ไหม
ถามชุมชน GitHub
ติดต่อฝ่ายสนับสนุน
ชอบด้วยกฎหมาย
© 2025 GitHub, อิงค์
เงื่อนไข
ความเป็นส่วนตัว
สถานะ
ราคา
บริการจากผู้เชี่ยวชาญ
บล็อก
