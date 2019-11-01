
<h1>현상]</h1>
<p>Mac OS high sierra &rarr;&nbsp;catalina(10.15) upgrade 후 jenkins 시작안됨</p>
<p><span style="color: rgb(51,51,51);">sudo launchctl load /Library/LaunchDaemons/org.jenkins-ci.plist 실행시 반응 없음</span></p>
<p><span style="color: rgb(51,51,51);">sudo launchctl load /Library/LaunchDaemons/org.jenkins-ci.plist 를 다시 실행시&nbsp;</span></p>
<p>Password:<br />/Library/LaunchDaemons/org.jenkins-ci.plist: service already loaded&nbsp;</p>
<p>메시지 표시됨</p>
<p><br /></p>
<h1>원인]</h1>
<p>start script 파일 org.jenkins-ci.plist 에 지정된 log 폴더가 존재하지 않아서 발생한 오류</p>
<p><br /></p><ac:structured-macro ac:name="code" ac:schema-version="1" ac:macro-id="456febd7-965c-42da-a566-9d277166008f"><ac:plain-text-body><![CDATA[<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
  <dict>
    <key>StandardOutPath</key>
    <string>/var/log/jenkins/jenkins.log</string>
    <key>StandardErrorPath</key>
    <string>/var/log/jenkins/jenkins.log</string>
    <key>EnvironmentVariables</key>
    <dict>
      <key>JENKINS_HOME</key>
      <string>/Users/Shared/Jenkins/Home</string>
    </dict>
    <key>GroupName</key>
    <string>daemon</string>
    <key>KeepAlive</key>
    <true/>
    <key>Label</key>
    <string>org.jenkins-ci</string>
    <key>ProgramArguments</key>
    <array>
      <string>/bin/bash</string>
      <string>/Library/Application Support/Jenkins/jenkins-runner.sh</string>
    </array>
    <key>RunAtLoad</key>
    <true/>
    <key>UserName</key>
    <string>jenkins</string>
    <key>SessionCreate</key>
    <true/>
  </dict>
</plist>]]></ac:plain-text-body></ac:structured-macro>
<p><br /></p>
<h1>해결방법]</h1>
<p>ref :&nbsp;<a href="https://stackoverflow.com/questions/39794811/jenkins-does-not-start-on-macos-10-12-sierra">https://stackoverflow.com/questions/39794811/jenkins-does-not-start-on-macos-10-12-sierra</a></p>
<p><br /></p>
<p>/var/log 폴더에 jenkins 폴더 생성후 owner를 jenkins로 변경</p><ac:structured-macro ac:name="info" ac:schema-version="1" ac:macro-id="feaed2b2-fd22-4fc5-b995-6a4b71f0942a"><ac:rich-text-body>
<p>sudo mkdir /var/log/jenkins</p>
<p>sudo chown jenkins:jenkins jenkins</p></ac:rich-text-body></ac:structured-macro>
<p><br /></p>
<p><span style="color: rgb(51,51,51);">sudo launchctl load /Library/LaunchDaemons/org.jenkins-ci.plist&nbsp; 로 실행시 /var/log/jenkins/jenkins.log 파일이 생성되는 것을 확인 할 수 있음.</span></p>
<p><br /></p>
