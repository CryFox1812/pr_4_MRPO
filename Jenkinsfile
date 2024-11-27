pipeline {
  agent any
  stages {
    stage(«Build») {
      steps {
        echo «Сборка приложения...»
        }
    }
  stage(«Test») {
    steps {
      echo «Тестирование приложения...»
      }
    }
  stage(«Deploy») {
    steps {
      echo «Развёртывание приложения...»
      }
    }
  }
  post {
      always {
          junit '**/target/*.xml'
      }
      failure {
          echo «Ошибка»
          mail to: «iwliev.roman@gmai.com»,
          subject: «${env.JOB_NAME} – Сборка № ${env.BUILD_NUMBER} провалилась»,
          body: «Для получения дополнительной информации о провале пайплайна, проверьте консольный вывод по адресу ${env.BUILD_URL}»
      }
  }
}
