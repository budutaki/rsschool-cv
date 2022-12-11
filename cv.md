# Elena Bugrova

## Contacts
**Phone:** +7 (985) 911-46-50  
**Telegram:** t.me/budutaki\
**Email:** bugrovael@gmail.com\
**GitHub:** github.com/budutaki\
**Discord:** Lena B(@budutaki)

## About me
Being experinced OPS manager I found myself interested in coding and decided to give it a go. I've learned the fundamentals of Java and already have some experince in back-end development, and now looking forward to get familiar with front-end as well.

## Skills
* JavaCore
* Spring Framework
* Git
* Github
* Gradle
* Maven
* JUnit

* Agile
* Scrum

## Code Example
*This server accepts connections in infinite loop, reads information in json format and adds tasks to to ToDo list.*
```
public class TodoServer {
    protected int port;
    protected Todos todos;

    public TodoServer(int port, Todos todos) {
        this.port = port;
        this.todos = todos;
    }

    public Task jsonToData(String json) throws ParseException {
        JSONParser jp = new JSONParser();
        GsonBuilder gb = new GsonBuilder();
        Gson gson = gb.create();
        JSONObject jsonObject = (JSONObject) jp.parse(json);
        return gson.fromJson(String.valueOf(jsonObject), Task.class);
    }


    public void start() throws RuntimeException {
        System.out.println("Starting server at " + port + "...");
        try (ServerSocket serverSocket = new ServerSocket(port)) {
            while (true) {
                try (Socket socket = serverSocket.accept();
                     BufferedReader in = new BufferedReader(new InputStreamReader(socket.getInputStream()));
                     PrintWriter out = new PrintWriter(socket.getOutputStream())) {

                    final String json = in.readLine();
                    final Task result = jsonToData(json);

                    switch (result.getType()) {
                        case ADD:
                            todos.addTask(result.getTask());
                            break;
                        case REMOVE:
                            todos.removeTask(result.getTask());
                            break;
                    }
                    out.println(todos.getAllTasks());
                }
            }
        } catch (IOException | ParseException e) {
            System.out.println("Не могу стартовать сервер");
            e.printStackTrace();
        }


    }
}
```
## Experience

**Senior Project Manager**\
NeuroArt Limited\
Nov 2022 - Present 

**Project Manager**\
Insideroom\
Sep 2021 - Nov 2022

**Operations Manager**\
Sema Educational center\
Sep 2020 - Sep 2021 

**Director of Operations**\
SilverSands Pvt Ltd\
Mar 2018 - Jan 2020 

## Education

**JS/FE Pre-school**\
RS School\
current time

**Java-developer**\
Netology.ru\
2021

**Strategic Leadership and Management Specialization**\
University of Illinois Urbana-Champaing\
2020

**Bachelor of Oriental Studies**\
Institute of Practical Oriental Studies\
2006

## Languages
English - Proficient\
Russian - Native


