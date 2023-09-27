1. Describe the Problem

As a user
So that I can record my experiences
I want to keep a regular diary

As a user
So that I can reflect on my experiences
I want to read my past diary entries

As a user
So that I can reflect on my experiences in my busy day
I want to select diary entries to read based on how much time I have and my reading speed

As a user
So that I can keep track of my tasks
I want to keep a todo list along with my diary

As a user
So that I can keep track of my contacts
I want to see a list of all of the mobile phone numbers in all my diary entries
# mobile numbers : start with a 0 and be 11 digits

2. Design the Class System

Consider diagramming out the classes and their relationships. Take care to focus on the details you see as important, not everything. The diagram below uses asciiflow.com but you could also use excalidraw.com, draw.io, or miro.com

# Nouns
experiences
Diary
Diary Entries

past_diary_entries

free_time
reading_speed

TaskTracker
Todo_list
list_complete
list_incomplete

phone_numbers
mobile_phone_list
# Verbs
record_experiences
read_past_experiences
select_diary_entries
mark_complete

Diary --> DiaryEntry 
TaskList --> Task
PhoneNumberExtractor
ReadableEntryFinder

Also design the interface of each class in more detail.



class Diary:
    # User-facing properties:
    #   tracks: list of instances of Track

    def __init__(self):
        pass # No code here yet

    def add(self, entry):
        # Parameters:
        #   entry: an instance of entry
        # Side-effects:
        #   Adds the entry to the entry property of the self object
        pass # No code here yet

    def all(self):
        # Returns:
        #   A list of the entries objects
        pass # No code here yet


class DiaryEntry:
    # User-facing properties:
    #   title: string
    #   contents: string

    def __init__(self, title, contents):
        # Parameters:
        #   title: string
        #   contents: string
        
        pass # No code here yet

    def format(self):
        # Returns:
        #   A string of the form "TITLE : Contents"
        pass 

class TaskList:
    # User-facing properties:
    #   title: string
    #   contents: string

    def __init__(self):        
        pass # No code here yet

    def add(self, todo):
        # Parameters:
        #   task: an instance of task
        # Returns:
        #    Nothing
        # Side-effects:
        # Adds the task to the task list
        pass 
    def incomplete(self):
        # Returns:
        #   A list of task instances representing the todos that are not complete
        pass
    def complete(self):
        # Returns:
        #   A list of task instances representing the todos that are complete
        pass

class Task:
    # User-facing properties:
    #   title: string
    #   contents: string

    def __init__(self, task):
        # Parameters:
        #   title: string
        #   contents: string
        
        pass # No code here yet

    def mark_complete(self):
        # Returns:
        #   Sets the tasks complete to True
        pass 

import re
class PhoneNumberExtractor:
    # User-facing properties:
    #   phone number: string
    

    def __init__(self):
        pass # No code here yet

    def extract_numbers(self, diary_entry):
        # Returns:
        #   numbers = re.findall(r'[0-9]+', diary_entry)
        #   self.numbers += numbers
            pass 
    def list_numbers(self):
        # Returns:
        #  list of phone numbers

class ReadableEntryFinder:
    def __init__(self):
        pass
    
    def estimate_reading_time(self, text):
        # words = text.split()
        # word_count = len(words)
        # returns
        # word_count / time

    











3. Create Examples as Integration Tests

Create examples of the classes being used together in different situations and combinations that reflect the ways in which the system will be used.

# EXAMPLE

"""
Given a library
When we add two tracks
We see those tracks reflected in the tracks list
"""
library = MusicLibrary()
track_1 = Track("Carte Blanche", "Veracocha")
track_2 = Track("Synaesthesia", "The Thrillseekers")
library.add(track_1)
library.add(track_2)
library.tracks # => [track_1, track_2]
4. Create Examples as Unit Tests

Create examples, where appropriate, of the behaviour of each relevant class at a more granular level of detail.

# EXAMPLE

"""
Given a track with a title and an artist
We see the title reflected in the title property
"""
track = Track("Carte Blanche", "Veracocha")
track.title # => "Carte Blanche"
Encode each example as a test. You can add to the above list as you go.

5. Implement the Behaviour

After each test you write, follow the test-driving process of red, green, refactor to implement the behaviour.