## Interactions

Interactions are objects that represent a user taking certain actions on App.net. For instance, when a User replies to a post, follows someone new, reposts or stars a post, an interaction is created. Interactions are very abstract objects that essentially form a sentence like: User X took action Y on object Z. If multiple users take the same action (multiple people reply to one post), the interaction will combine those events into one interaction. Here are some sample interactions:

* @dalton and @berg reposted post 1

    {
        "action": "repost",
        "objects": [
            {
                ...post 1..
            }
        ],
        "users": [
            {
                ...@berg's user object...
            },
            {
                ...@dalton's user object...
            },
        ]
    }

* @berg started following user 1

    {
        "action": "follow",
        "objects": [
            {
                ...user 1...
            }
        ],
        "users": [
            {
                ...@berg's user object...
            }
        ]
    }

* @berg starred post 1

    {
        "action": "star",
        "objects": [
            {
                ...post 1...
            }
        ],
        "users": [
            {
                ...@berg's user object...
            }
        ]
    }

* @berg replied to post 1

    {
        "action": "reply",
        "objects": [
            {
                ...post 1...
            }
        ],
        "users": [
            {
                ...@berg's user object...
            }
        ]
    }


### Interactions Fields

<table>
    <thead>
        <tr>
            <th>Field</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>action</code></td>
            <td>string</td>
            <td>What ```users``` did. Currently one of ```follow```, ```reply```, ```repost```, or ```star```</td>
        </tr>
        <tr>
            <td><code>objects</code></td>
            <td>list</td>
            <td>A list of objects that ```users``` took ```action``` on. These objects will be Users if ```action=follow``` otherwise they will be Posts.</td>
        </tr>
        <tr>
            <td><code>users</code></td>
            <td>list</td>
            <td>A list of User objects that took ```action``` on ```objects```.</td>
        </tr>
    </tbody>
</table>