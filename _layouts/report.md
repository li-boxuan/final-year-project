---
---

<!DOCTYPE html>
<html>
	<head>
		<title>{{ page.student }} | Project Report (Ongoing) </title>
		<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.min.js"></script>
        <link rel="stylesheet" href="resources/style.css">
        <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/materialize/0.100.1/css/materialize.min.css">
        <link rel="stylesheet" href="https://rawgit.com/coala/coalaCSS/master/coala.css">
        <script src="https://cdnjs.cloudflare.com/ajax/libs/materialize/0.100.1/js/materialize.min.js"></script>
        <link href="https://fonts.googleapis.com/css?family=Roboto+Mono:300,300i,400,400i,700,700i|Roboto:100,200,300,400,500,600,700,800,900|Ubuntu+Mono|Overpass+Mono|Inconsolata" rel="stylesheet">
        <link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">
        <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css" rel="stylesheet">
	</head>
	<body class='report'>
		<div class="container">
        <br>
            <div class="row no-margin">
                <div class="col m12">
                    <h4 class="left light">HKU CS 2018-2019 Final Year Project Website</h4>
                </div>
                <br>
            </div> 
            <br>
            <div class="row no-margin">
                <div class="col m6">
                    <div class="card flex1">
                        <div class="card-content">
                            <h5 class="light no-margin"><a href="{{page.organisation_link}}">{{ page.organisation }}</a></h5>
                            <h3 class="light">{{ page.project }}</h3>
                            <p>{{page.bio | markdownify}}</p>
                        </div>
                    </div>
                </div>
                <div class="col m3">
                    <div class="card flex1">
                        <div class="card-content">
                            <div class="center"><h4 class="light no-margin">Student</h4></div>
                            <br>
                            <div class="center">{{ page.student | markdownify }}</div>
                        </div>
                    </div>
                    <div class="card flex1">
                        <div class="card-content">
                            <div class="center"><h4 class="light no-margin">Supervisor</h4></div>
                            <br>
                            <div class="center">{{ page.mentors  | markdownify }}</div>
                        </div>
                    </div>
                </div>
                <div class="col m3">
                    <div class="card flex1">
                        <div class="card-content links-section">
                            {% for ih in page.social %}
                                <div class="link">
                                {% for item in ih %}
                                    <div class="row no-margin ">
                                        <div class="col m6">{{item[0]}}</div>
                                        <div class="col m6"><a href="{{item[1][1]['link']}}">{{item[1][0]['username']}}</a></div>
                                    </div>
                                {% endfor %}
                                </div>
                                {% if forloop.last == false %}<div class="divider"></div>{% endif%}
                            {% endfor %}
                            <br>
                            <div class="row no-margin center">
                                <div class="col m3"><i class="fa fa-envelope-o"></i></div>
                                <div class="col m9">{{ page.email }}</div>
                            </div>

                        </div>
                    </div>
                </div>
            </div>
            <br>

            <div class="row no-margin">
                <div class="col m2">
                    <div class="card flex1">
                        <div class="card-content">
                            <div class="center"><h5 class="light no-margin">Online System</h5></div>
                            <br>
                            <div class="center"><a href="{{ page.system }}">View website</a></div>
                        </div>
                    </div>
                </div>
                <div class="col m2">
                    <div class="card flex1">
                        <div class="card-content">
                            <div class="center"><h5 class="light no-margin">System Demo</h5></div>
                            <br>
                            <div class="center"><a href="{{ page.video }}">View video</a></div>
                        </div>
                    </div>
                </div>
                <div class="col m2">
                    <div class="card flex1">
                        <div class="card-content">
                        <div class="center"><h5 class="light no-margin">Phase 1</h5></div>
                        <br>
                        <div class="center"><a href="https://li-boxuan.github.io/final-year-project/plan.pdf">View Project Plan</a></div>
                        </div>
                    </div>
                </div>
                <div class="col m2">
                    <div class="card flex1">
                        <div class="card-content">
                        <div class="center"><h5 class="light no-margin">Phase 2</h5></div>
                        <br>
                        <div class="center">Interim Report (TODO)</div>
                        </div>
                    </div>
                </div>
                <div class="col m2">
                    <div class="card flex1">
                        <div class="card-content">
                        <div class="center"><h5 class="light no-margin">Phase 3</h5></div>
                        <br>
                        <div class="center">Final Report (TODO)</div>
                        </div>
                    </div>
                </div>
            </div>  
            <br>

            <div class="no-margin">
                <table class="padding-table">
                    <thead class="no-border">
                        <tr class="blue-grey-text text-lighten-2">
                            <td>Period</td>
                            <td>Progress Description</td>
                        </tr>
                    </thead>
                    <tbody class="card activity">
                        {% for activities in page.activity %}
                        {% for a in activities %} 
                           <tr>
                                <td>{{ a[1][0]["period"] | markdownify}}</td>
                                <td>{{ a[1][1]["details"] | markdownify}}</td>
                           </tr>
                        {% endfor %}
                          
                        {% endfor %}
                    </tbody>

                </table>
  
            </div>
            <br>
            <div class="content card">
                <div class="card-content">
                    {{page.content  | markdownify }}
                </div>
            </div>
            <br><br>


		</div>
	</body>
</html> 

