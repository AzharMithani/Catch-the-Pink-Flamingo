# Catch-the-Pink-Flamingo
Designing a Data Model for 'Catch the Pink Flamingo'

# For 2nd Prompt 




Nodes : 3, Edges :6

Vertex properties:User (properties): Name, UID, TeamId, Grade, Achievements
Chat Session (properties): SessionID, Number of Users, StartTime, EndTime, Open or Closed, ChatTitle, ActiveStatus (e.g Active, Inactive)
ChatText: Alphabets, Numbers, words, paragraphs, Emoticons, lines, Special Charecters, UID, TimeStamp
- Edge Properties:
Leaves: TimeStamp, Reason (e.g. network failure / quit the session), session id 
Joins: TimeStamp, Session ID, ChatTitle
Starts: TimeStamp, Session ID, ChatTitle
Writes: TimeStamp, Session ID, ChatTitle, MessageLength
Mentions: TimeStamp, Session ID, ChatTitle, Indication
Contains
-
1.Which teams are having more conversations? A: Analysing the combination of Chat Session properties, Joins, Writes, Mentions, Starts properties of each Chat Title we can analyse whether the teams are having more conversations.
E.g. Analyse the the graph community to determine which community have more connections between the users of each group.The more dense the community the more they chat.

2.Do users chat more (or less) before they leave a team?A: By analysing combination of properties in User, Chat Session, Chat Text, Joins, Starts, Writes, Mentions, Leaves we can calculate whether users chat more (or less) before they leave a team.
E.g. For each chat, collect all the userID of the chatting team at the beginning of the chat and at the end of the chat. Compute the subsets of leaving users and remaining users. Measure the average chatting amount at each subset of users. Mark as yes if the average of the leaving is grater than the average of the remaining.

3.What are the dominant terms (words) used in a chat session within a specific time period?A: By analysing the combination of properties of Chat session, Chat text one can determine the dominant terms (words) used in that particular chat session
E.g. Collect all Chat Text entities of a specific chat session  for a time period and execute a word count in descending order over the collection. Pick the top 10 fromt he list and that will be the answer.

4.Which users are most active in a specific chat session?A: By analysing the combination of properties of User, Chat session, Chat text, Writes and Mentions the algorithm can determine which user is most active in a specific chat session
E.g.For the session, determine the density of writes from a user to that chat session. 

5.How many chat sessions is a user participating in at the same time?A: By analysing the combination of properties of User, Chat Session, Starts and Leaves the algorithm should identify the number if chat sessions a particular user is participating.


E.g. Analyze the "Joins" entity for a user by time period and determine the number of active sessions.
