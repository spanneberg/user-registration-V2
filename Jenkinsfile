node {
  git url: 'https://github.com/spanneberg/user-registration-V2.git', branch: 'jenkins2'

  def mvnHome = tool 'Maven3'

  // build Parent POM and actual application w/ unit tests
  stage 'Commit'
  sh "${mvnHome}/bin/mvn -pl .,user-registration-application clean install"

  stage 'Acceptance'
  sh "${mvnHome}/bin/mvn -pl user-registration-acceptancetest-jbehave clean install"

  stage 'Performance'
  sh "cd user-registration-capacitytest-gatling && ${mvnHome}/bin/mvn clean install"

}
