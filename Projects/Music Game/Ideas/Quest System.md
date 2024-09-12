---
dg-publish: true
---
class_name Quest manager extends Node

var quest_list: Array = []
var active_quests:Array = []



class_name Quest extends Resource

var trigger_list: Array[Trigger]
var criteria: Array[Criterion]
var segments: Array[Quest_Segment]

class Trigger:
	var trigger_type: Quest_Triggers
	enum Quest_Triggers = {
	LOCATION, TIME, NPC, OBJECT, QUEST } # previous quest completed
	
	var trigger_value

class Criterion:
	enum Quest_Critera_Types ={ 
		TIME, 
		LOCATION, # character/object at location, including inventory
		RELATIONSHIP, 
		STATE, # character state, including emotions, 
	}

class Quest_Segment:
	enum Quest_Segment_Types = {
		CUTSCENE, 
		NPC, # talk to npc
		OBJECT, # pick up an object
		LOCATION, # Go to location, or bring object to location
		KNOWLEDGE, # e.g. learn a song, or identify a spirit,
	- ACTION, # e.g sing song, do ceremony
	}
	var quest_segment_type: Quest_Segment_Types
	var quest_segment_value
	var quest_segment_description



func start():
	for trigger in trigger_list:
		
	

Quest Assembly
- 
- onTrigger:
	- for c in criterea:
		- if true, 