### Nest.js使用swagger

- `yarn add @nestjs/swagger swagger-ui-express`

- 使用

  ```js
  import { NestFactory } from '@nestjs/core';
  import { AppModule } from './app.module';
  import { DocumentBuilder, SwaggerModule } from '@nestjs/swagger';
  
  async function bootstrap() {
    const app = await NestFactory.create(AppModule);
    app.setGlobalPrefix('api');
    const options = new DocumentBuilder()
      .setTitle('博客API')
      .setDescription('测试用')
      .setVersion('1.0.0')
      .build();
  
    const document = SwaggerModule.createDocument(app, options)
    SwaggerModule.setup('api', app, document)
  
    await app.listen(3000);
  }
  
  bootstrap();
  
  ```

  

