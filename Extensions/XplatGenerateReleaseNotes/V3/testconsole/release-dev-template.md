# Notes de version    

**Application** : {{releaseDetails.releaseDefinition.name}} <br/>
**Version** : $(Version)#{{buildDetails.id}} <br/>
**Numéro de livraison**  : {{releaseDetails.name}} <br/>
**Date** : {{date releaseDetails.modifiedOn "YYYY-MM-DD"}} <br/> 


{{#group workItems by="fields['Custom.Type']"}}


{{#forEach items}}

{{#eq (lookup this.fields 'System.WorkItemType') "User Story"}}

{{#if isFirst}}
# Catégorie : {{lookup this.fields 'Custom.Type'}}
{{/if}}
*  **{{this.id}}** - **{{lookup this.fields 'System.Tags'}}** {{lookup this.fields 'System.Title'}}
   - {{{lookup this.fields 'Custom.Notesdeversion'}}}


{{/eq}}

{{/forEach}}


{{/group}}


# Commits
{{#forEach commits}}
{{#startsWith "Merge " this.message}}
{{else}}
* **Message:** {{this.message}}  
   -  **Commited by:** {{this.author.displayName}} 
{{/startsWith}}
{{/forEach}}







