<!DOCTYPE html>
<html>
<head>
    <title>Event List</title>
</head>
<body>
    <h1>Event List</h1>
    <ul>
        {% for event in events %}
            <li>{{ event.name }} - {{ event.date }} - {{ event.location }} <a href="{% url 'event_delete' event.pk %}">Delete</a></li>
        {% endfor %}
    </ul>
    <a href="{% url 'event_create' %}">Add Event</a>
</body>
</html>
<!DOCTYPE html>
<html>
<head>
    <title>Create Event</title>
</head>
<body>
    <h1>Create Event</h1>
    <form method="post">
        {% csrf_token %}
        {{ form.as_p }}
        <button type="submit">Save</button>
    </form>
</body>
</html>
<!DOCTYPE html>
<html>
<head>
    <title>Delete Event</title>
</head>
<body>
    <h1>Delete Event</h1>
    <p>Are you sure you want to delete "{{ event.name }}"?</p>
    <form method="post">
        {% csrf_token %}
        <button type="submit">Confirm</button>
    </form>
</body>
</html>
