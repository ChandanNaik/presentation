<!-- effect=stars-->

# Hello  Sibros !

---
<!-- fg=white bg=black -->

# Introduction



- Born and raised in the Silicon Valley of India (Bengaluru, India) 🇮🇳

- Bachelor’s degree in Information Science and Engineering from BMS College of Engineering

- Master’s degree in Computer Science from University of Colorado Boulder (SkoBuffs!) 🏔️

- I have over 3+ years of experience as a Full Stack Engineer
	- Worked at both budding startups and large organizations

- I love building things and I’m most attracted to solving real world problem with large scale impact!

- Currently working as Full Stack Developer for Microgrid Labs

---
<!-- fg=white bg=black -->
# Computers
![](images/msDOS.jpg)

---
<!-- fg=white bg=black -->

## Journey 🛣️
- Started with DOS Games (1998)
	- Dave 🤩
	- Mario

- Internship at IISc (2014)
	- Text To Speech system in native Indian Languages (Kannada and Tamil)

- Navigation System for Blind (2015)

---
<!-- fg=white bg=black -->

# Interests and Hobbies

- Calligraphy ✍️
- Cooking 👨‍🍳
- Used to play Competative Badminton 🏸
- Newfound interest in XR (Extended Reality)
	- Currently working on building my ideas in AR and VR space in my free time

---

<!-- fg=green bg=black -->
# Lets get Technical!

---
<!-- fg=green bg=black -->
## Problem Statement

Build a reliable and robust backend system for the vehicle simulation algorithms

---
<!-- fg=green bg=black -->

# My approach

---
<!-- fg=green bg=black -->

## What technologies to use?
- Python, Django, Flask, MongoDB, Celery, Nginx

## How long do you have to build this?
- Less than three months

## What are the bare minimum requirements of the system?
- Four simulation algorithms
- Cater to atleast 50-100 concurrent users

---
<!-- fg=red bg=black -->

# Challenges
![](images/challenges.jpeg)

---
<!-- fg=red bg=black -->

## 1. Learning a new framework in a short span of time

- Django
- Django Rest Framework
- Celery

---
<!-- fg=red bg=black -->

## 2. Design Choices

- Microservices
- Cloud Deployment: AWS(EC2, Cloudwatch)
- Security
	- Session token authorization for API
	- HTTPs based security mechanism for authentication
- Performance
- Scalability
	- Horizontal Scaling: More traffic => More Resources
	- Caching: Cache read only data to reduce latency, ORM based caching for application

--- 
<!-- fg=red bg=black -->

## 3. Django

- Parsing deeply nested JSON data in Django(ORM)
```
@api_view(['POST'])
def my_view():
    ....
    my_data = 
    {
        'album_name': 'The Grey Album',
        'artist': 'Danger Mouse',
        'tracks': [
            {'order': 1, 'title': 'Public Service Announcement', 'duration': 245},
            {'order': 2, 'title': 'What More Can I Say', 'duration': 264},
            {'order': 3, 'title': 'Encore', 'duration': 159},
        ]
    }
    serializer = AlbumSerializer(data= my_data)
    serializer.is_valid()
    ....
```
---
<!-- fg=green bg=black -->

## 3.1 Solution

```
class TrackSerializer(serializers.ModelSerializer):
    class Meta:
        model = Track
        fields = ['order', 'title', 'duration']

class AlbumSerializer(serializers.ModelSerializer):
    tracks = TrackSerializer(many=True)

    class Meta:
        model = Album
        fields = ['album_name', 'artist', 'tracks']

    def create(self, validated_data):
        tracks_data = validated_data.pop('tracks')
        album = Album.objects.create(**validated_data)
        for track_data in tracks_data:
            Track.objects.create(album=album, **track_data)
        return album
```

--- 
<!-- fg=red bg=black -->

## 4. Deployment

- Nginx: Web Serving, Caching, Load Balancing(Future), Microservice IPC
- AWS linux EC2 instance 

---
<!-- fg=magenta bg=black -->
<!-- effect=fireworks -->

# Impact 

- Brought two new customers to the business
- Tie up with a major energy industry

---

<!-- fg=cyan bg=black -->

# Takeaways

---

<!-- fg=cyan bg=black -->

## 1. Documentation is Gold

- Fast Learner 🚀
- Stack Overflow, Developer Documents

---

<!-- fg=cyan bg=black -->

## 2. First hand experience of building things from scratch

- Self starter
- Learnt a lot of new technical skills
	- Frontend: D3, UI/UX design(Figma)
	- Backend: Django, DRF, Celery, node
	- Database: MySQL, MongoDB
	- App Server: IIS/Nginx
	- Test Driven Development

---
<!-- fg=cyan bg=black -->

## 3. Software is Easy, people are hard

- Managing people is not an easy task
- Being an effective communicator

---

<!-- fg=cyan bg=black -->

## 4. Perseverance

```
while(noSuccess){
	self.tryAgain()
	if(Dead)
		break
}
```


---
<!-- effect=stars-->

Thank You ! ❤️