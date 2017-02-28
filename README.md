# MMM-Hello-Mirror
Voice-Control for the MagicMirror based in Google Speech Recognizer (annyang)

This an extension for the [MagicMirror](https://github.com/MichMich/MagicMirror) to send notifications to other modules on voice commands.

## Installation
1. Navigate into your MagicMirror's `modules` folder
2. Execute `git clone https://github.com/Matzefication/MMM-Hello-Mirror.git`
3. No `npm install` is needed
4. (Re)start magic mirror (e.g. with `pm2 restart mm`)

# Using the module
To use this module, add it to the modules array in the `config/config.js` file:

```javascript
modules: [
    {
        module: 'MMM-Hello-Mirror',
        position: 'lower_third', // If you want to see the prompt and recognised speech, omit otherwise
        config: {
            // See 'Configuration options' for more information.
        }
    }
]
```

## Configuration Options
The following properties can be configured:

<table width="100%">
	<thead>
		<tr>
			<th>Option</th>
			<th width="100%">Description</th>
		</tr>
	<thead>
	<tbody>
		<tr>
			<td><code>language</code></td>
			<td>
				The language used.
				<br>
				<br><b>Valid values:</b> 
				<br><code>en</code>
				<br><code>de</code>
				<br>
				<br><b>Default value:</b> <code>de</code>
			</td>
		</tr>
		<tr>
			<td><code>voice</code></td>
			<td>
				The voice used.
				<br>
				<br><b>Valid values:</b> 
				<br><code>UK English Female</code>
				<br><code>UK English Male</code>
				<br><code>US English Female</code>
				<br><code>Deutsch Female</code>
				<br>
				<br><b>Default value:</b> <code>Deutsch Female</code>
			</td>
		</tr>		
	</tbody>
</table>

## Working with voice commands
A voice command has to start with `Hey (magic) mirror` following your individual command. After recognizing a command, a notification will be send with the following params:

- notification identifier: `VOICE_COMMAND`
- notification payload: `the spoken command` (without "Hey (magic) mirror")
