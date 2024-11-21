---
jcr-language: en_us
title: AI-powered search in Adobe Learning Manager
description: Learn about the AI-powered search in Adobe Learning Manager
exl-id: 9982a8be-b2e6-42a4-836a-7f9337588ae8
---
# Advanced AI search in Adobe Learning Manager 

The Search functionality in ALM enhances the user experience by allowing them to find relevant content efficiently and help them consume the right content.

Adobe Learning Manager introduces an AI-powered search capability that combines lexical and semantic search. The search is smarter, as it looks for specific terms and understands the context and intent behind them. The advanced AI-powered search understands the meaning of your query and provides relevant results.  

>[!NOTE]
>
>AI powered search is only available for the Learners.

## Why is search important?

Search functionality is important for several reasons:

* **User Experience**: A well-implemented search feature enhances user satisfaction by allowing users to quickly find the information they need.
* **Efficiency**: It saves time by reducing the effort required to locate specific content, especially in large databases or learning management systems.
* **Accessibility**: Effective search capabilities make information more accessible, ensuring that users can engage with content relevant to their needs.
* **Personalization**: Advanced search systems can tailor results based on user preferences, improving the relevance of the information presented.

## Evolving search behaviors on the web

As people search online, the way they search is changing, and search engines are adjusting to keep up. The following are some key ways people search for information nowadays:

* **Intent-Driven**: Instead of typing exact keywords, users now express their needs with phrases like I want to or I need to. Modern search engines understand the purpose behind these phrases and give more relevant results.
* **Ranked Results**: Search results are organized based on what other users found helpful. This means the most useful content appears at the top, making it easier to find quality information.
* **Multiple Sources**: The more sources a search engine covers, the better the results. By pulling information from a variety of trusted sources, search engines provide more complete and accurate answers.
* **Personalized**: Search engines adjust results based on factors like time, location, and user preferences. This makes it easier for users to find information that fits their specific needs at the moment.

## Why Adobe Learning Manager's search is better

Adobe Learning Manager offers a smarter, more advanced search experience that not only matches the keywords but contextually understands the meaning of the user query to find the most relevant results for them.

* **AI-Powered**: Adobe Learning Manager uses advanced AI techniques to understand the meaning behind search intent and not just the words. This helps show results that really match what the user wants, making searches more accurate.
* **Peer-Driven**: Adobe Learning Manager uses a range of course quality parameters to rank the most useful results. This ranking algorithm is trained on 50 million data points that periodically scores every content in the repository
* **Comprehensive**: Adobe Learning Manager searches the entire library, including own content, third-party course titles, descriptions, tags, personalized notes and other metadata. For content like Video and PDF, it automatically transcribes and searches within their transcript.

## Adobe Learning Manager's AI-powered search

Adobe Learning Manager uses advanced AI technology to enhance the search experience and make it easier to find relevant learning content. The major components of advanced search are described below.

### Recognizing key terms

Adobe Learning Manager uses Natural Language Processing (NLP) to identify the important keywords from course titles and descriptions. It then focuses on those keywords to provide better search results, helping boost the results with those keywords over other results. For example, if a learner searches for **PhotoShop Basics**, Adobe Learning Manager will prioritize the word **PhotoShop** to show the most relevant courses.

![](assets/search-2.png)
_Prioritize the keyword_

In the screenshot above, a learner searches for courses using the term **PhotoShop getting started**. The search prioritizes the word **PhotoShop** to find the most relevant courses around **PhotoShop**. For the keyword getting started, it understands the intent and looks for similar words to show the best matches. This way, the learner sees courses that focus on PhotoShop and are suitable for beginners.

### Expanding the query

Adobe Learning Manager expands the user query to more contextual meaning to help find better results. This way the search algorithm gets more context along with the user query. Even if learners use general terms, they can still find useful results. For example, if a learner is searching for **Customer service foundations**, it tries to find the keyword from the query and expand the rest of the query to similar phrases. 

![](assets/search-1.png) 
_Expanding the query_

### Course metadata search

Adobe Learning Manager's metadata search covers metadata from both native and imported courses (e.g. from LinkedIn Learning or Go1). This capability searches through your course titles, descriptions, tags, personalized notes, and other metadata. This helps make the results better and more accurate by using a lot of different metadata to find results. 
Note: Customer data, including content and transcripts, is not shared with any external service for AI-powered search. All content is stored within the current storage system.

### Semantic search

Adobe Learning Manager now incorporates semantic search alongside traditional lexical search, enhancing the accuracy of search results. By generating vector embeddings from course titles and descriptions, it creates a comprehensive vector database. When a learner submits a query, the system vectorizes the query and performs similarity matching to identify the most relevant results. For example, if a learner searches for beginner PhotoShop tutorial, the system understands the request and finds courses that are especially helpful for PhotoShop beginners .

![](assets/semantic-search.png)
_Semantic search_

>[!NOTE]
>
>Semantic search currently supports only English content. 

### In-Content search

Adobe Learning Manager's search functionality has been enhanced to search through actual content. It automatically transcribes videos, audio files, and PDFs, incorporating those transcripts into search results. Additionally, it utilizes Adobe Connect meeting recordings to provide more comprehensive and relevant results. This enhancement ensures that courses containing rich content like videos and meeting notes are included, significantly improving search accuracy and effectiveness. 

>[!NOTE]
>
>Newly added content, such as videos or PDFs, will be available for in-content search after a 24-hour processing period. 

### AI-Powered search and re-ranking 

Adobe Learning Manager's search is a leader in the industry, using a unique mix of advanced technologies to provide top-quality results. It combines traditional search methods (such as phrase matching), sophisticated semantic search, and in-content search to produce comprehensive results. These results are ranked by key course quality factors such as enrollments, publication dates, ratings, popularity, and more, ensuring that the highest-quality matches from all indices, guided by our course quality ranking system.

Overall, ALM's AI-powered search is made to be thorough, accurate, and easy to use, helping learners quickly find exactly what they need to support their learning journey.


>[!NOTE]
>
>1. Customers using a headless implementation need to follow the API documentation to enable Advanced search
>2. Advanced search is currently not available for the Salesforce app.
>3. Customer data, including content and transcripts, is not shared with any external service for AI-powered search. All content remains securely stored within the existing storage system.
