# Backend Project Readme

This backend project is developed using PostgreSQL, NestJS, and TypeScript. It offers various features and functionalities to manage article summaries through links and URLs. The project utilizes the OpenAI API to extract data and summarize articles.

## Features and Functionality

### 1. Create Summary via Link and URL

The project provides an API endpoint that allows users to create summaries by providing a link or URL to an article. The backend system will fetch the content of the article using the provided link and then use the OpenAI API to generate a summary of the article. Users can easily access this API to create concise summaries of articles they find interesting.

### 2. Extract Data and Article Content

The "Create Summary" API not only generates a summary but also extracts relevant data and article content from the provided link. This data could include metadata, article title, author information, and other useful details. By leveraging the OpenAI API, this functionality ensures that users get comprehensive information about the articles they summarize.

### 3. Get All Summarized Articles

Another API endpoint is available to retrieve a list of all the previously summarized articles. This allows users to access their summarized articles and manage them efficiently.

### 4. Delete Articles by Particular ID

The project includes an API endpoint that enables users to delete a specific article based on its ID. This functionality helps users to remove articles they no longer need or want to keep in the system.

## Technologies Used

- PostgreSQL: The relational database management system used to store and manage the summarized articles and related data.
- NestJS: A progressive Node.js framework used to build the backend APIs in a modular and scalable manner.
- TypeScript: The programming language used to develop the backend application, providing static typing and improved code readability.
- OpenAI API: The OpenAI API is utilized to perform article summarization, extracting relevant data from articles.

## Getting Started

To set up and run the project on your local machine, follow these steps:

1. Clone the repository from https://github.com/ramanbhola22/bbc-summarize.git.

   ```
   git clone https://github.com/ramanbhola22/bbc-summarize.git
   cd frontend
   ```

2. Install the required dependencies using the following command:

   ```
   npm install
   ```

3. Set up the PostgreSQL database and update the connection configuration in the project to point to your database.

4. Obtain an API key from OpenAI to access their API services for article summarization.

5. Create .env file in root directory on backend and Update your data

   ```bash

     DB_HOST='YOUR DB HOST NAME'
     DB_PORT='YOUR PORT NAME'
     DB_USER='YOUR USER NAME'
     DB_PASS='YOUR USER PASSWORD'
     DB_DIALECT=postgres
     DB_NAME_DEVELOPMENT='YOUR DATABASE NAME'
     OPENAI_API='YOUR OPEN AI API KEY'

   ```

6. Start the application using the following command:

   ```
   npm run start:dev
   ```

This will start the development server and launch the application in your default web browser. You can access it at `http://localhost:4000/`.

## API Documentation

Sure, here's the API documentation formatted in Markdown for easy readability:

### Create Summary

Endpoint: `/api/v1/articles/create-summary`
Method: `POST`

Request Body:

```json
{
  "links": ["ARTICLE_LINK_OR_URL"]
}
```

Response:

```json
{
  "title": "Article title",
  "content": "SUMMARIZED_ARTICLE_CONTENT",
  "source": "Source of content like: bbc.com",
  "url": "article link"
}
```

### Get All Summarized Articles

Endpoint: `/api/articles`
Method: `GET`

Response:

```json
{
  "articles": [
    {
      "id": "ARTICLE_ID",
      "title": "Article title",
      "content": "SUMMARIZED_ARTICLE_CONTENT",
      "source": "Source of content like: bbc.com",
      "url": "article link"
    },
    ...
  ]
}
```

### Delete Article by ID

Endpoint: `/api/articles/:id`
Method: `DELETE`

Response:

```json
{
  "message": "Article with ID ARTICLE_ID has been deleted successfully."
}
```

Please note that you can replace `ARTICLE_LINK_OR_URL`, `ARTICLE_ID`, `Article title`, and `SUMMARIZED_ARTICLE_CONTENT` with actual values when making API requests or handling responses.

## Contribution

We welcome contributions to improve and enhance this project. If you find any issues or have ideas to make it better, please feel free to create a pull request or submit an issue on the [GitHub repository](https://github.com/ramanbhola22/bbc-summarize.git).

## License

This project is licensed under the [MIT License](LICENSE).
