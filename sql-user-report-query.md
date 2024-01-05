SELECT
  TO_CHAR(chats.created_at, 'YYYY-MM-DD HH24:MI:SS') AS created_at,
  chats.id, 
  status,
  email,
  last_name,
  first_name,
  user_request,
  response
FROM users
JOIN conversations ON users.id = conversations.user_id
JOIN chats ON chats.conversation_id = conversations.id
ORDER BY chats.created_at DESC;